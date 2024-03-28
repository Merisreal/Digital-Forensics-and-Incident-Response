### NTUSER:

Every time you make a change to the look and behavior of Windows and installed programs, whether that's your desktop background, monitor resolution, or even which printer is the default, Windows needs to remember your preferences the next time it loads.

### Recent Files

In NTUSER

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs`

Registry Explorer cho phép sort, nên những cái nào sử dụng gần nhất, sẽ ở top

Tìm .pdf, .jpg, .docx bằng command:

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs\.pdf`

## **Office Recent Files:**

`NTUSER.DAT\Software\Microsoft\Office\VERSION`

Version:

`NTUSER.DAT\Software\Microsoft\Office\15.0\Word`

15.0 → Office 2013

User’s live id

`NTUSER.DAT\Software\Microsoft\Office\VERSION\UserMRU\LiveID_####\FileMRU`

## **ShellBags:**

Cấu trúc lưu trữ của windows:

- Thông tin về cách thức quản lí tệp (File Explorer), các thư mục và tập tin, cỡ của cửa sổ, vị trí, chiều rộng,…

`USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\Bags`

`USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\BagMRU`

`NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU`

`NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags`

### **Open/Save and LastVisited Dialog MRUs:**

Khi lưu hay mở, hộp thoại hỏi lưu hay save chỗ nào → Windows sẽ nhớ nó → Có thể tìm được thông tin này

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU`

## **Windows Explorer Address/Search Bars:**

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths`

`NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery`
