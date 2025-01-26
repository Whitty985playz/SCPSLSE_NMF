![Screenshot 2025-01-26 142109](https://github.com/user-attachments/assets/493252fc-df3f-43e3-8823-51447993a4e7)
# No More Foundation Protocal
SCP: Secret Laboratory Scripted Events Script "No More Foundation" is intented for ADMINISTRATOR ONLY USE.

This was created as a way for Server Administrators to end a round if it has gone on for too long with out a Dead Man's Switch or Auto Nuke.

> [!NOTE]
> It is recommended that you do **not** create a ***Player Console Command*** for this script.

## How to Install:
- Install **Scripted Events**(Can be found in the ***REQUIRED PLUGINS*** Folder) to your server.
- Install [Audio Player](https://github.com/Edren-Baton-Team/AudioPlayer/releases/) and its dependencies to your server.
- Download and Extract **NMF.zip** in your downloads.
  - This is becuase there is another *.zip* file and 2 .ogg files inside of **NMF.zip**
    - Scripted events Exiled 9 is not released on GitHub but is released publicly.
- Take **NoMoreFoundation.zip** and extract it in your Scripted Events Scripts Directory.
  - Extract it here: ***/.config/EXILED/config/ScriptedEvents/Scripts***
- take the 2 .ogg files and put them in the Audio Player's Audio folder.
  - This can be found in **/.config/EXILED/plugins/audio**
- Restart your server and test using "run NMF"

## What does the script do?
The No More Foundation protocol spawns an Overpowered Tutorial Insurgency with one task. To end the round.
If the mission fails, all of the facility warheads will automatically detonate themselves, killing everybody inside and outside the facility.

## Configs
Audio configs can be found on lines 3-20 in the MAIN SCRIPT.

Default Audio Config:
```# AUDIO PLUGIN IS REQUIRED FOR THIS TO WORK, DOWNLOAD THE PLUGIN AND DEPENDENCIES HERE: https://github.com/Edren-Baton-Team/AudioPlayer/releases/
COMMAND /audio add 1

# ONLY CHANGE THE SECOND NUMBER TO CHANGE THE OUTPUT VOLUME
COMMAND /audio volume 1 15
COMMAND /audio play 1 .config/EXILED/Plugins/audio/Train_Enter.ogg

WAIT SEC 13

# IT IS NOT RECOMENDED TO CHANGE THE CASSIE TEXT, ONLY CHANGE THE TRANSLATION AFTER THE "|" IF YOU WANT TO CHANGE THE LANGUAGE.
CASSIE SILENT pitch_0.3 .g4 .g5 pitch_0.8 N M F Insurgency HASENTERED . WAITING FOR TERMINATION OF pitch_0.1 .g3 .g3 pitch_0.6 {HUMANS} PERSONNEL | <color=#aa00ff><b>N.M.F. Insurgency Has Entered The Facility.</color></b><split><color=#aa00ff><b>Waiting for Termination Of {HUMANS} Personnel.

WAIT SEC 1
WAIT MIL 5
COMMAND /audio volume 1 25
# ONLY CHANGE "AUDIO.ogg" TO THE SONG FILE YOU WANT TO BE PLAYED.
# WARNING: File must actually start at 11 seconds in. Concider adding a build up or something that matches the audio you want for a seemless transition.
COMMAND /audio play 1 .config/EXILED/Plugins/audio/AUDIO.ogg
```

Teleport Configs can be found on lines 35-37 in the MAIN SCRIPT.

Default Teleport Config:
```# CHANGE THE COORDENATES ACCORDING TO WHERE YOU WANT THE TUTORIALS TO SPAWN ON SURFACE ZONE
TPX {TUTORIAL} -40.89 992 -36
WAIT MIL 1
```

The item + Effect configs can be found on lines 39-61 on the MAIN SCRIPT.

Default IE Config:
```# CHANGE THE ITEMS ACCORDING TO HOW OVER POWERED YOU WANT THEM TO BE.
# REMEMBER: YOU WANT THE TUTORIALS TO BE OVERPOWERED AS THIS IS ONLY TO BE USED IF THE ROUND HAS BEEN OCCURING TOO LONG WITH OUT A DEAD MAN'S SWITCH.
ITEM ADD {TUTORIAL} KeycardO5
WAIT MIL 1
ITEM ADD {TUTORIAL} ArmorHeavy
WAIT MIL 1
ITEM ADD {TUTORIAL} ParticleDisruptor
WAIT MIL 1
ITEM ADD {TUTORIAL} GrenadeHE
WAIT MIL 1
ITEM ADD {TUTORIAL} GrenadeHE
WAIT MIL 1
ITEM ADD {TUTORIAL} GrenadeHE
WAIT MIL 1
ITEM ADD {TUTORIAL} GunFRMG0
WAIT MIL 1
EFFECT ADD {TUTORIAL} Scp1344 1 0
WAIT MIL 1
EFFECT ADD {TUTORIAL} Invigorated 1 0

# IT IS NOT RECOMMENDED TO CHANGE THE MOVEMENT SPEED
WAIT MIL 1
EFFECT ADD {TUTORIAL} MovementBoost 255 0
```
