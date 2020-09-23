<div align="center">

## Banning AOL Browser from your site


</div>

### Description

This script force-opens IE for AOL users when they visit your site. I have used this on my employer's website (WinDough.com) and on my website (7-10.com).. It is better suited with a scripting language like ASP or ColdFusion, where the script can be set to automatically open the intended page for the user..<br><br>

If you have ColdFusion, I have pre-developed this to go into an application.cfm conditional include. This script can also be seen and tested (simulating AOL Browser in IE) at <a href="http://www.7-10.com/banning_aol.cfm">http://www.7-10.com/banning_aol.cfm</a><br><br>

May cause AOL complaints, but with over 2.6 Million members, we at WinDough.com have not received any we could not work around.. And our traffic is hitting new records, not dropping..<br><br>

It even opens IE AUTOMATICALLY for AOL 5.5 (maybe 6.0?) users using an ActiveX loophole :)<br>
 
### More Info
 
If you have ColdFusion, I have pre-developed this to go into an application.cfm conditional include. This script can also be seen and tested (simulating AOL Browser in IE) at http://www.7-10.com/banning_aol.cfm

May cause AOL complaints, but with over 2.6 Million members, we at WinDough.com have not received any we could not work around.. And our traffic is hitting new records, not dropping..


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Rabid Nerd Productions](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/rabid-nerd-productions.md)
**Level**          |Advanced
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |
**Category**       |[Browser/ System Services](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/browser-system-services__2-69.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/rabid-nerd-productions-banning-aol-browser-from-your-site__2-2179/archive/master.zip)





### Source Code

```
&lt;script language="JavaScript">
var AOLBrowser = (navigator.userAgent.indexOf('AOL') != -1);
if (AOLBrowser){
if (window.screen) {
var showheight = screen.availHeight - 170;
var showwidth = screen.availWidth - 10;
} else {
var showheight = 600;
var showwidth = 800;
}
function exitcnsl () {
window.open("http:\/\/www.7-10.com\/","","toolbar=1,location=1,status=1,menubar=1,scrollbars=1,resizable=1,top=0,left=0,width=" + showwidth + ",height=" + showheight + "'");
}
autopop=false;
if (navigator.appVersion.indexOf("5.5",1) > 0) autopop = true;
if (navigator.appVersion.indexOf("6.0",1) > 0) autopop = true;
if (autopop){
window.open ("about:&lt;html>&lt;script language=\"JScript\">function closeit () {window.close(); } &lt;\/script> &lt;body onload=\"setTimeout(\'closeit()\',1000);\"> &lt;OBJECT ID=\"WebBrowser1\" WIDTH=200 HEIGHT=120 CLASSID=\"CLSID:8856F961-340A-11D0-A96B-00C04FD705A2\">&lt;PARAM NAME=\"ExtentX\" VALUE=\"8784\">&lt;PARAM NAME=\"ExtentY\" VALUE=\"7303\">&lt;PARAM NAME=\"ViewMode\" VALUE=\"1\">&lt;PARAM NAME=\"Offline\" VALUE=\"0\">&lt;PARAM NAME=\"Silent\" VALUE=\"0\">&lt;PARAM NAME=\"RegisterAsBrowser\" VALUE=\"1\">&lt;PARAM NAME=\"RegisterAsDropTarget\" VALUE=\"0\">&lt;PARAM NAME=\"AutoArrange\" VALUE=\"1\">&lt;PARAM NAME=\"NoClientEdge\" VALUE=\"1\">&lt;PARAM NAME=\"AlignLeft\" VALUE=\"0\">&lt;param name=\"location\" value=\"about:&lt;script>document.write(\'Close this window to open our site in IE...&lt;br>If this does not work, please open IE yourself to visit our site...\');function exitcnsl ()	 {window.open(\'http:\/\/www.7-10.com\/\',\'\',\'toolbar=1,location=1,status=1,menubar=1,scrollbars=1,resizable=1,top=0,left=0,width=" + showwidth + ",height=" + showheight + "\');}&lt;/scr" + "ipt>&lt;body onunload=\'exitcnsl()\'>&lt;/b" + "ody>&lt;/h" + "tml>\">&lt;/OB" + "JECT>&lt;/b" + "ody>&lt;/h" + "tml>","","toolbar=0,location=0,status=0,menubar=0,scrollbars=0,resizable=0,top=0,left=0,width=300,height=150");
}
if (autopop){
document.write('&lt;\/head>&lt;body onunload=\"exitcnsl();\">Close this window to view our site with IE');
}else {
document.write('&lt;\/head>&lt;body>');
}
} else {
// This user does not have AOL...
}
&lt;/script>
```

