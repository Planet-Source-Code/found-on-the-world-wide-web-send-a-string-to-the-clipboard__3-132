<div align="center">

## Send a string to the clipboard


</div>

### Description

Without using OLE...

Michael Pickens mfc_faq@stingray.com
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Found on the World Wide Web](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/found-on-the-world-wide-web.md)
**Level**          |Intermediate
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |C\+\+ \(general\)
**Category**       |[System Services/ Functions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/system-services-functions__3-23.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/found-on-the-world-wide-web-send-a-string-to-the-clipboard__3-132/archive/master.zip)





### Source Code

```
CString str = "Some text";
::OpenClipboard(this->m_hWnd);
::EmptyClipboard();
HGLOBAL h = GlobalAlloc(GHND | GMEM_SHARE, str.GetLength() + 1);
strcpy((LPSTR)GlobalLock(h), str);
GlobalUnlock(h);
::SetClipboardData(CF_TEXT, h);
::CloseClipboard();
```

