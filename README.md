# Youtube_Freemium

[Last 10 Videos Website Example](https://i-am-jakoby.github.io/Youtube_Minus/) <-- Example of loading results into a webpage as a way to promote your last 10 videos Ad FREE

---

# Syntax 

## This loads the functions you need into your console 
The way I understand how this works is, that the commands pulls the commands from following url:
jakoby.lol/ytfreemium as found below.
We can avoid security risks, by simply hosting this website locally and then point to that instead.
That way we at least are in control of the source code and avoid being hacked.

`Invoke-RestMethod jakoby.lol/ytfreemium` <-- use this to look at the code without executing it

```powershell
Invoke-RestMethod jakoby.lol/ytfreemium | Invoke-Expression
```

---

## Watch individual video
```powershell
watchvideo -url "https://www.youtube.com/watch?v=VJVrzAeH-0I"
```

---

## Watch newest video from specific creator
```powershell
watchvideo -creator iamjakoby
```

<img src= https://github.com/I-Am-Jakoby/Youtube_Minus/blob/main/Assets/watchURL.png width="300" alt="C#" />

---

## Watch last X amount of videos from specific creator
```powershell
watchVideo -creator NetworkChuck -maxResults 4
```

<img src= https://github.com/I-Am-Jakoby/Youtube_Minus/blob/main/Assets/vidx4.png width="300" alt="C#" />

---

## Get New Video From all Creators on List

Watch the newest video from all creators in specified list (Ex list below)

With future plans of being able to load in custom lists general hacking, bug bounties, malware research etc 

Does not have to stay in cyber either, make custom music lists etc

```powershell
$channels         = @{
    NetworkChuck = "UC9x0AN7BWHpCDHSm9NiJFJQ"
    JohnHammond  = "UCVeW9qkBjo3zosnqUbG7CFw"
    Stok         = "UCQN2DsjnYH60SFBIA6IkNwg"
    Hak5         = "UC3s0BtrBJpwNDaflRSoiieQ"
    Nahamsec     = "UCCZDt7MuC3Hzs6IH4xODLBw"
    Zsecurity    = "UCVPjtOVcnKaSRI8IO3KSetA"
    Sasquach     = "UCUoJk48pujh29p8zLsnD5PQ"
    iamjakoby    = "UCQUz2mC5Regc63XRWEqD9FA"    
}
```

```powershell
watchVideo -creator all
```

<img src= https://github.com/I-Am-Jakoby/Youtube_Minus/blob/main/Assets/allVids.png width="300" alt="C#" />

---

## CLI Format

This function will return an object with some basic information on the creators newest video 

This gives you an idea of the variables we can play with for future functions 

Getting only live videos from a list of creators 

Getting only videos posted today from a list of creators etc 

---

```
newvideo -creator JohnHammond
```

<img src= https://github.com/I-Am-Jakoby/Youtube_Minus/blob/main/Assets/newVideoSyntax.jpg width="900" alt="C#" />

---

## Get-ChannelID 

Use this to get a youtube Channel ID from a youtube url
```powershell
$channelURL = "https://www.youtube.com/iamjakoby"
    
$pageInfo = Invoke-RestMethod $channelURL
    
Get-ChannelID -channelURL $pageInfo
```
