新编地图汉化简明教程
============  
一、工具介绍
============
1. 文本编辑器：依然是推荐[Everedit](http://www.everedit.cn/)  
2. 地图打包/解包工具：[最萌小汐](https://github.com/syj2010syj)大婶写的[w3x2txt](https://github.com/syj2010syj/w3x2txt)  
3. 地图优化工具：[wc3mapmax](https://github.com/actboy168/wc3mapmax)  
  
二、汉化步骤
============
1. 解包：
  1. 用[w3x2txt](https://github.com/syj2010syj/w3x2txt)对目标地图解包，把目标地图拖到“工具-地图打包解包.bat”这个文件上，然后等一会儿会在目标地图目录下生成一个文件夹里面包含目标地图的所有文件。  	
  2. [w3x2txt](https://github.com/syj2010syj/w3x2txt)会把传统*地图内部*的“war3map.w3x”文件转换成“war3map.w3x.ini”格式，方便使用文本编辑器编辑。  
2. 汉化：  
  1. 汉化物编：
============ 
两个部分：   
   (1). 先任意打开解包一个地图，我以*fateanother3.0N(韩文地图比较有代表性，因为在非韩文版本魔兽下韩文显示是不正常的)*为例子,将地图解包后，先打开一个ini文件："war3map.w3a.ini"。  
   (2). 抓住两个关键词就能完成物编文件的汉化：
   "name"：  
   "name"是技能/物品/科技/魔法效果等等的名字，这个东西你汉化不汉化都一样因为仅仅是在物编里面显示，并不在实际游戏中显示。  
  "tip"：  
  "tip"一般是各种提示工具，例如："Tip"、 "Ubertip"、 "Researchtip" 、"Researchubertip",一般汉化这些项就算到位了。  
(3). wts部分：  
直接文本编辑器打开然后把需要汉化文本的汉化了就行，一般是这样的格式：
STRING XXX
{
  <字符串体>
}
(4).w3i部分：
打开“war3map.w3i.ini”进行汉化即可。
(5).游戏平衡常数文件部分：
打开“war3mapskin.txt”进行汉化。
 2. 汉化j文件：
============ 
jass函数参数部分：
	 ```jass
    native S2I  takes string s returns integer
    native S2R  takes string s returns real
    native SubString takes string source, integer start, integer end returns string
    native SubString takes string source, integer start, integer end returns string
    native StringLength takes string s returns integer
    native StringCase takes string source, boolean upper returns string
    native StringCase takes string source, boolean upper returns string
    native StringHash takes string s returns integer
    native GetLocalizedString takes string source returns string
    native GetLocalizedString takes string source returns string
    native GetLocalizedHotkey takes string source returns integer
    native SetMapName           takes string name returns nothing
    native SetMapDescription    takes string description returns nothing
    native ExecuteFunc          takes string funcName returns nothing
    native          ChangeLevel         takes string newLevel, boolean doScoreScreen returns nothing
    native          LoadGame            takes string saveFileName, boolean doScoreScreen returns nothing
    native          SaveGame            takes string saveFileName returns nothing
    native          RenameSaveDirectory takes string sourceDirName, string destDirName returns boolean
    native          RenameSaveDirectory takes string sourceDirName, string destDirName returns boolean
    native          RemoveSaveDirectory takes string sourceDirName returns boolean
    native          CopySaveGame        takes string sourceSaveName, string destSaveName returns boolean
    native          CopySaveGame        takes string sourceSaveName, string destSaveName returns boolean
    native          SaveGameExists      takes string saveName returns boolean
    native  InitGameCache    takes string campaignFile returns gamecache
    native SetDayNightModels            takes string terrainDNCFile, string unitDNCFile returns nothing
    native SetDayNightModels            takes string terrainDNCFile, string unitDNCFile returns nothing
    native SetSkyModel                  takes string skyModelFile returns nothing
    native SetIntroShotText             takes string introText returns nothing
    native SetIntroShotModel            takes string introModelPath returns nothing
    native PlayModelCinematic           takes string modelName returns nothing
    native PlayCinematic                takes string movieName returns nothing
    native ForceUIKey                   takes string key returns nothing
    native SetAltMinimapIcon            takes string iconPath returns nothing
    native CreateTrackable      takes string trackableModelPath, real x, real y, real facing returns trackable
    native SetCinematicCamera           takes string cameraModelFile returns nothing
    native SetCineFilterTexture             takes string filename returns nothing
    native NewSoundEnvironment          takes string environmentName returns nothing
    native CreateSound                  takes string fileName, boolean looping, boolean is3D, boolean stopwhenoutofrange, integer fadeInRate, integer fadeOutRate, string eaxSetting returns sound
    native CreateSound                  takes string fileName, boolean looping, boolean is3D, boolean stopwhenoutofrange, integer fadeInRate, integer fadeOutRate, string eaxSetting returns sound
    native CreateSoundFilenameWithLabel takes string fileName, boolean looping, boolean is3D, boolean stopwhenoutofrange, integer fadeInRate, integer fadeOutRate, string SLKEntryName returns sound
    native CreateSoundFilenameWithLabel takes string fileName, boolean looping, boolean is3D, boolean stopwhenoutofrange, integer fadeInRate, integer fadeOutRate, string SLKEntryName returns sound
    native CreateSoundFromLabel         takes string soundLabel, boolean looping, boolean is3D, boolean stopwhenoutofrange, integer fadeInRate, integer fadeOutRate returns sound
    native CreateMIDISound              takes string soundLabel, integer fadeInRate, integer fadeOutRate returns sound
    native SetMapMusic                  takes string musicName, boolean random, integer index returns nothing
    native PlayMusic                    takes string musicName returns nothing
    native PlayMusicEx                  takes string musicName, integer frommsecs, integer fadeinmsecs returns nothing
    native PlayThematicMusic            takes string musicFileName returns nothing
    native PlayThematicMusicEx          takes string musicFileName, integer frommsecs returns nothing
    native GetSoundFileDuration         takes string musicFileName returns integer
    native AddSpecialEffect             takes string modelName, real x, real y returns effect
    native AddSpecialEffectLoc          takes string modelName, location where returns effect
    native AddSpecialEffectTarget       takes string modelName, widget targetWidget, string attachPointName returns effect
    native AddSpecialEffectTarget       takes string modelName, widget targetWidget, string attachPointName returns effect
    native AddSpellEffect               takes string abilityString, effecttype t, real x, real y returns effect
    native AddSpellEffectLoc            takes string abilityString, effecttype t,location where returns effect
    native AddSpellEffectTarget         takes string modelName, effecttype t, widget targetWidget, string attachPoint returns effect
    native AddSpellEffectTarget         takes string modelName, effecttype t, widget targetWidget, string attachPoint returns effect
    native AddLightning                 takes string codeName, boolean checkVisibility, real x1, real y1, real x2, real y2 returns lightning
    native AddLightningEx               takes string codeName, boolean checkVisibility, real x1, real y1, real z1, real x2, real y2, real z2 returns lightning
    native GetAbilityEffect             takes string abilityString, effecttype t, integer index returns string
    native GetAbilityEffect             takes string abilityString, effecttype t, integer index returns string
    native GetAbilitySound              takes string abilityString, soundtype t returns string
    native GetAbilitySound              takes string abilityString, soundtype t returns string
    native CreateImage                  takes string file, real sizeX, real sizeY, real sizeZ, real posX, real posY, real posZ, real originX, real originY, real originZ, integer imageType returns image
    native Cheat            takes string cheatStr returns nothing
    native Preload          takes string filename returns nothing
    native PreloadGenEnd    takes string filename returns nothing
    native Preloader        takes string filename returns nothing
	```
以上是cj函数，bj里面的函数我就不列出了。（参数是明文的就汉化，不是明文的就忽略，返回值是string的不用管肯定不是明文）。
	```jass
	funcntion config takes nothing returns nothing
	call SetMapName()
	call SetMapDescription()
	......
	endfunction
	```
*以上两个函数自行判断是否需要汉化。*
__特别注意__:
如果jass函数的参数是：**STRING XXX** 或者 **TRIGSTR XXX** 这样的形式，代表它的字符串文本在wts文件中，请参照上面的教程汉化！

三、重新打包
============
把修改过的文件按原路径替换回文件夹然后把整个文件夹拖到bat上就可以重新打包了。

四、优化地图
============
[wc3mapmax](https://github.com/actboy168/wc3mapmax)怎么使用小汐大婶已经说过了，这里不再赘述。

教程到此结束，如果有什么漏掉的错误的欢迎指正。








