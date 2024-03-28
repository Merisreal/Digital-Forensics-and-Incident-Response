### **Disk Image:**

Khi một file được xóa, hệ thống không thực sự xóa data của file đó ngay lập tức → nó chỉ ghi đè thông tin về vị trí của ập tin đó trên ổ đĩa ở table hay database → Ko còn có một liên kết trực tiếp giữa tên tệp và dữ liệu thực sự của nó trên đĩa 

→ Dữ liệu vẫn tồn tại ở đó cho đến khi nó được ghi đè bởi dữ liệu mới 

Ví dụ: khi xóa file document.txt. Dữ liệu  trong document.txt vẫn còn tồn tại trên đĩa, nhưng ko được liên kết với tên của nó nữa

→ Tiếp theo tạo New_document.txt dữ liệu mới của tập tin này được lưu vào vùng trống trên ổ đĩa mà document.txt đã sử dụng 

→ data của document bị ghi đè bởi New_document

Eric Zimmerman’s tool

## **Windows Prefetch files**

Khi windows chạy ứng dụng, thông tin của nó sẽ được lưu → thường dùng để tải chương trình nhanh khi xài thường xuyên

→ C:\Windows\Prefetch → .pf

→ Gồm có :

- Thời gian chạy cuối cùng
- số lần được chạy
- Bất kỳ file hay device được chạy bởi file

⇒ dùng để truy suất thông tin các tệp được sử dụng gần đây

**Folder:**

```c
C:\Windows\Prefetch
```

**(PECmd.exe) from Eric Zimmerman's tools** 

`PECmd.exe -f <path-to-Prefetch-files> --csv <path-to-save-csv>`

or with directory:

`PECmd.exe -f <path-to-Prefetch-files> --csv <path-to-save-csv>`

```c
Examples: PECmd.exe -f "C:\Temp\CALC.EXE-3FBEF7FD.pf"
          PECmd.exe -f "C:\Temp\CALC.EXE-3FBEF7FD.pf" --json "D:\jsonOutput" --jsonpretty
          PECmd.exe -d "C:\Temp" -k "system32, fonts"
          PECmd.exe -d "C:\Temp" --csv "c:\temp" --csvf foo.csv --json c:\temp\json
          PECmd.exe -d "C:\Windows\Prefetch"

```

## **Windows 10 Timeline**

Các ứng dụng và tệp được sử dụng gần đây → Windows 10 Timeline 

- thời gian được thực thi
- thời gian tập trung cho ứng dụng đó

**Folder:**

```c
C:\Users\<username>\AppData\Local\ConnectedDevicesPlatform\{randomfolder}\ActivitiesCache.db

```

 **Eric Zimmerman's JLECmd.exe**

WxTCmd.exe -f <path-to-timeline-file> --csv <path-to-save-csv>

```c
Examples: WxTCmd.exe -f "C:\Users\eric\AppData\Local\ConnectedDevicesPlatform\L.eric\ActivitiesCache.db" --csv c:\temp

          Database files are typically found at 'C:\Users\\AppData\Local\ConnectedDevicesPlatform\L.\ActivitiesCache.db'

          Short options (single letter) are prefixed with a single dash. Long commands are prefixed with two dashes
```

## **Windows Jump Lists**

ứng dụng được ghim trên taskbar → Các file được mở trong các ứng dụng đó

**Folder:**

```c
C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations

```

 **Eric Zimmerman's JLECmd.exe**

`JLECmd.exe -f <path-to-Jumplist-file> --csv <path-to-save-csv>`

```c
Examples: JLECmd.exe -f "C:\Temp\f01b4d95cf55d32a.customDestinations-ms" --mp
          JLECmd.exe -f "C:\Temp\f01b4d95cf55d32a.automaticDestinations-ms" --json "D:\jsonOutput" --jsonpretty
          JLECmd.exe -d "C:\CustomDestinations" --csv "c:\temp" --html "c:\temp" -q
          JLECmd.exe -d "C:\Users\e\AppData\Roaming\Microsoft\Windows\Recent" --dt "ddd yyyy MM dd HH:mm:ss.fff"
```

## **Shortcut Files**

Lối tắt cho mỗi tệp được mở. Chứa thông tin về lần mở đầu tiền và cuối cùng, đường dẫn của file được mở cùng

```c
C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\

C:\Users\<username>\AppData\Roaming\Microsoft\Office\Recent\

```

Eric Zimmerman's LECmd.exe (Lnk Explorer)

⇒ chỉ cho file có đuổi *.lnk

```c
Examples: LECmd.exe -f "C:\Temp\foobar.lnk"
          LECmd.exe -f "C:\Temp\somelink.lnk" --json "D:\jsonOutput" --jsonpretty
          LECmd.exe -d "C:\Temp" --csv "c:\temp" --html c:\temp --xml c:\temp\xml -q
          LECmd.exe -f "C:\Temp\some other link.lnk" --nid --neb
          LECmd.exe -d "C:\Temp" --all
```

## **IE/Edge history**

auto spy

```c
C:\Users\<username>\AppData\Local\Microsoft\Windows\WebCache\WebCacheV*.dat

```

## **Jump Lists**

Lần cuối các file được mở. 

```c
C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations

```
