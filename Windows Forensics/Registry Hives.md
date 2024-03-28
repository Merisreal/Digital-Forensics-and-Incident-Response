# Registry Hives

Registry tập hợp các cơ sở dữ liệu chứa cấu hình của hệ thống. Những dữ liệu cấu hình này về: phần cứng, phần mềm, thông tin người dùng, rêcntly used files, device connect,…..

Reistry hive: Gồm một nhóm khóa, khóa con (subkey), và các giá trị của register hỗ trợ được tải vào khi máy tính khởi động 

- Mỗi lần có new user log on, thì hive mới được tạo riêng cho mỗi user đó - user profile hive

| Registry hive | Supporting files |
| --- | --- |
| HKEY_CURRENT_CONFIG | System, System.alt, System.log, System.sav |
| HKEY_CURRENT_USER | Ntuser.dat, Ntuser.dat.log |
| HKEY_LOCAL_MACHINE\SAM | Sam, Sam.log, Sam.sav |
| HKEY_LOCAL_MACHINE\Security | Security, Security.log, Security.sav |
| HKEY_LOCAL_MACHINE\Software | Software, Software.log, Software.sav |
| HKEY_LOCAL_MACHINE\System | System, System.alt, System.log, System.sav |
| HKEY_USERS\.DEFAULT | Default, Default.log, Default.sav |

**Structure of the Registry:**

| Folder/predefined key | Description |
| --- | --- |
| HKEY_CURRENT_USER | Contains the root of the configuration information for the user who is currently logged on. The user's folders, screen colors, and Control Panel settings are stored here. This information is associated with the user's profile. Viết tắt là HKCU. |
| HKEY_USERS | Contains all the actively loaded user profiles on the computer. HKEY_CURRENT_USER is a subkey of HKEY_USERS. HKEY_USERS Viết tắt là  HKU. |
| HKEY_LOCAL_MACHINE | Contains configuration information particular to the computer (for any user). Viết tắt là HKLM. |
| HKEY_CLASSES_ROOT | Is a subkey of HKEY_LOCAL_MACHINE\Software. The information that is stored here makes sure that the correct program opens when you open a file by using Windows Explorer. This key is sometimes abbreviated as HKCR.
Starting with Windows 2000, this information is stored under both the HKEY_LOCAL_MACHINE and HKEY_CURRENT_USER keys. The HKEY_LOCAL_MACHINE\Software\Classes key contains default settings that can apply to all users on the local computer. The HKEY_CURRENT_USER\Software\Classes key has settings that override the default settings and apply only to the interactive user.
The HKEY_CLASSES_ROOT key provides a view of the registry that merges the information from these two sources. HKEY_CLASSES_ROOT also provides this merged view for programs that are designed for earlier versions of Windows. To change the settings for the interactive user, changes must be made under HKEY_CURRENT_USER\Software\Classes instead of under HKEY_CLASSES_ROOT.
To change the default settings, changes must be made under HKEY_LOCAL_MACHINE\Software\Classes .If you write keys to a key under HKEY_CLASSES_ROOT, the system stores the information under HKEY_LOCAL_MACHINE\Software\Classes.
If you write values to a key under HKEY_CLASSES_ROOT, and the key already exists under HKEY_CURRENT_USER\Software\Classes, the system will store the information there instead of under HKEY_LOCAL_MACHINE\Software\Classes. |
| HKEY_CURRENT_CONFIG | Contains information about the hardware profile that is used by the local computer at system startup. |

**Có 2 cách truy cập Registry:**

1. Command: regedit.ext
2. Folder: C:\Windows\System32\Config
    1. **DEFAULT** (mounted on `HKEY_USERS\DEFAULT`)
    2. **SAM** (mounted on `HKEY_LOCAL_MACHINE\SAM`)
    3. **SECURITY** (mounted on `HKEY_LOCAL_MACHINE\Security`)
    4. **SOFTWARE** (mounted on `HKEY_LOCAL_MACHINE\Software`)
    5. **SYSTEM** (mounted on `HKEY_LOCAL_MACHINE\System`)
    
    https://sec.vnpt.vn/2021/04/windows-forensic-registry-analysis-part1/
    
    ### Hives chứa thông tin user
    
    NTUSER.DAT (  HKEY_CURRENT_USER khi user login )
    
    - C:\Users\<username>\
    
    USRCLASS.DAT ( HKEY_CURRENT_USER\Software\CLASSES)
    
    - C:\Users\<username>\AppData\Local\Microsoft\Windows
    
    ⇒ Cả 2 đều là hidden files
    
    ### Amcache Hive
    
    - C:\Windows\AppCompat\Programs\Amcache.hve
    
    ⇒ quan trọng lưu lại thông tin các ứng dụng chạy thường xuyên
    
    ### **Transaction Logs and Backups**
    

Transcation log ghi lại các thay đổi trong registry hive. được sử dụng khi ghi lại dữ liệu và registry hive → nó có thể có những thay đổi mới nhất ở registry , do chúng chưa được đưa vào registry hive

→ Dưới dạng .LOG trong cùng thư mục với Registry hives đó

VD: log của SAM trong C:\Windows\System32\Config, sẽ tên là SAM.LOG trong thư mục của SAM  → có thể có nhiều LOG1, LOG2,..

Registry Backup ngược lại, Bản sao của các hives, trong C:\Windows\System32\Config → copy → C:\Windows\System32\Config\RegBack 10 ngày/ lần → Thuận tiện cho việc xem lại thay đổi
