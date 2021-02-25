# The-PP-festival-is-coming

The link to the site :
https://twilightyabhi1.wixsite.com/theppstore



If anythings wrong in the Gituniverse, its not my fault, im not a git user.. its my first time here ..
And i cant host this in air: If you KNow how to lemme knoe.

Yours sincerly 
Chintu Jr,
PP marketer .







; The Below code is a shit to work with..it really took the toll on me.. Activate this hellish great ( looking ugly) code only if u wish to make life easier by shotcut spamming everywhere you go and click your mouse with. Well, 1024 shotcuts in a tab.. Crazy fucking good..

; The following will activate the power of 1000 lemons { VIM ULTRA PRO MAX } all at once...( not kidding you.. this can actually handle 1024 shotcuts in its bin..LOL!!!) THE LEMON LAUNCHER..( as i named her So..HEHEEE)

/*
		
SetWorkingDir,%A_ScriptDir%
FileInstall,LemonLaunchSettings.ini,LemonLaunchSettings.ini,1

#SingleInstance,Force
#InstallKeybdHook
SetBatchLines,-1
SetControlDelay,-1
CoordMode,Pixel
FileGetSize,SettingsSize,LemonLaunchSettings.ini
FileGetTime,SettingsTime,LemonLaunchSettings.ini
Global Setup:=[],History:=[]

Search:=[],Direct:=[],IniReadWrite("LemonLaunchSettings.ini"),Temp:=[]
For i in Search
	Temp[A_Index]:="search " i
For i in Direct
	Temp.Insert(i)
Temp.Remove("search")

If !Setup["Hotkey"]{
	MsgBox,0,No Hotkey Found,No Hotkey Found`nPlease Set a Hotkey,2
	ExitApp
}else{
	(Setup["Separator"]?"":Setup["Separator"]:="|")
	Hotkey,% Setup["Hotkey"],Hotkey,On
	If Setup["VoiceHotkey"]
		Hotkey,% Setup["VoiceHotkey"],Voice,On
}return

Hotkey:
	If Setup["ColorMatch"]
		SetTimer,PGColor,50
	PreWin:=WinActive("A")
	If !WinExist(Setup["Title"]){
		If Setup["Trans"]
			Gui,Color,F0F0F0,F0F0F0
		Gui,Font,% (Setup["TextSize"]?"s" Setup["TextSize"]:"") (Setup["TextWeight"]?" w" Setup["TextWeight"]:"") (Setup["TextColor"]?" c" Setup["TextColor"]:"")
		Gui,Add,Progress,% "x0	y0 w" Setup["w"] " h" Setup["h"] " BackgroundF0F0F0 Disabled vBGP"
		Gui,Add,Edit,% "x" (Setup["Identifier"]?23:0) " y0 w" Setup["w"]-(Setup["Identifier"]?23:0) " h" Setup["h"] (Setup["Trans"]?" -E0x200":"") " -0x40 vData"
		If Setup["Identifier"]{
			Gui,Add,Progress,% "x0	y0 w" Setup["h"] " h" Setup["h"] " Disabled vIdentifierP"
			Gui,Font,s10 w700
			Gui,Add,Text,% "x0 y0 w" Setup["h"] " h" Setup["h"] " BackgroundTrans Center vIdentifierT",LL
			Gui,Font,% (Setup["TextSize"]?"s" Setup["TextSize"]:"") (Setup["TextWeight"]?" w" Setup["TextWeight"]:"") (Setup["TextColor"]?" c" Setup["TextColor"]:"")
		}Gui,Add,Button,Default Hidden gOK
		Gui,-Caption +ToolWindow +AlwaysOnTop +LastFound hwndHWND
		Gui,Show,% "x" Setup["x"] " y" Setup["y"] " w"	Setup["w"] " h" Setup["h"],%	Setup["Title"]
		If Setup["Trans"]
			WinSet,TransColor,F0F0F0
	}else If !WinActive(Setup["Title"]){
		Gui,+LastFound
		GuiControl,Show,IdentifierP
		GuiControl,Show,IdentifierT
		WinActivate
		WinWaitActive
		GuiControl,Focus,Data
		SendInput,^a
}return
