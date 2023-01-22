[![EN](https://user-images.githubusercontent.com/9499881/33184537-7be87e86-d096-11e7-89bb-f3286f752bc6.png)](https://github.com/r57zone/DualShock4-emulator/) 
[![RU](https://user-images.githubusercontent.com/9499881/27683795-5b0fbac6-5cd8-11e7-929c-057833e01fb1.png)](https://github.com/r57zone/DualShock4-emulator/blob/master/README.RU.md)
[![FR](https://user-images.githubusercontent.com/9499881/147121779-f90bdadf-8009-4dc4-8682-f15f4bd2008e.png)](https://github.com/r57zone/DualShock4-emulator/blob/master/README.FR.md)

# Émulateur DualShock 4
Cette application qui permet d'émuler la manette DualShock 4 de chez Sony en utilisant une manette XBox ou clavier/souris. Cette méthode est nécessaire pour un fonctionnement complet du service [Sony Playstation Plus](https://www.playstation.com/fr-fr/explore/playstation-now/) ou [Playstation Remote Play](https://www.playstation.com/remote-play/). Elle fonctionne grace au pilote [ViGEm](https://github.com/ViGEm).

## Installation
1. Installer [ViGEmBus](https://github.com/ViGEm/ViGEmBus/releases).
2. Installer [Microsoft Visual C++ Redistributable 2017](https://learn.microsoft.com/cpp/windows/latest-supported-vc-redist) ou plus récent.
3. Dézipper et lancer "DS4Emulator.exe" (**Attention!** Il est important de lancer l'exe avant Playstation Plus si vous utilisez la manette XBox, pour que PS Plus donne la priorité à la manette (virtuelle) DS4).
4. Lancez "PlayStation Plus", "PS Remote Play", "xCloud" ou une autre application. Lisez la FAQ pour configurer xCloud.
5. Si besoin, vous pouvez inverser les axes : changez les paramètres `InvertX` et `InvertY` en `1` dans le fichier de configuration `Config.ini`.
6. Vous pouvez également vérifier le fonctionnement de l'émulation du contrôleur DualShock 4 dans le programme [VSCView](https://github.com/Nielk1/VSCView/releases/). Pour émuler à partir du clavier et de la souris, vous devez également modifier le paramètre `ActivateInAnyWindow` sur `1` et redémarrer le programme.

## FAQ
**• Le programme se ferme après le lancement**<br>
"Antivirus" bloque le chargement dynamique de la bibliothèque de gamepads Xbox, de sorte que le programme se bloque. Vous pouvez le fermer pendant la durée d'utilisation.



**• Les touches du pavé tactile ne fonctionnent pas**<br>
Il est possible que les applications "PS Plus" ou "PS Remote Play" aient donné la priorité à la manette Xbox, alors redémarrez les applications "PS Plus" ou "PS Remote Play" et le DualShock 4 émulé devrait avoir priorité sur la manette Xbox .



**• Lorsque vous jouez dans xCloud, dans le navigateur, le menu contextuel est appelé avec le bouton droit de la souris, comment puis-je le supprimer dans le navigateur ?**<br>
Changez d'abord le nom de la fenêtre dans le fichier de configuration ou changez le paramètre `ActivateInAnyWindow` en `1`, en redémarrant le programme. Ensuite, allez sur le site Web xCloud, appuyez sur "F12", sélectionnez la console et collez-y [ce code](https://github.com/r57zone/DualShock4-emulator/blob/master/ContextMenuBlock.txt), appuyez sur Exécuter et le menu contextuel ne sera plus affiché.



• **Le jeu voit 2 manettes en même temps (manette DualSense / DualShock 4 / Nintendo Pro ou JoyCons et Xbox)**<br>
Vous pouvez masquer votre manette de jeu à l'aide du programme [HidHide](https://github.com/ViGEm/HidHide).

## Manette Xbox
Le bouton `Retour/Vue/Select` émule l'appui sur le `Touchpad` sur une manette Sony DualShock 4.

L'appuie simultané sur le bouton `Retour/Vue/Select` et le bouton `Start` (ou touche `F12`) émule l'appui sur le bouton `Share`.

Par défaut, le bouton `Xbox` ouvre la XBox Gamebar, si vous souhaitez que celui-ci émule le bouton `PS`, il faut d'abord désactiver la Gamebar dans vos paramètres Windows. Pour simuler un appui sur le bouton `PS`, appuyez sur `Retour/Vue/Select` + `LB` ou `F2`

Vous pouvez émuler une secousse de la manette (gyroscope) en appuyant sur `Retour/Vue/Select` et `RB`.


Vous pouvez faire pivoter la manette (gyroscope) en appuyant sur `Back` et `DPAD ←↑↓→` (vous pouvez modifier les combinaisons dans le fichier de configuration).


Si nécessaire, vous pouvez intervertir entre `RB-RT` et `LB-LT` ainsi que le bouton `Share` et l'appui sur le `Touchpad` en changeant `SwapTriggersShoulders` ou `SwapShareTouchPad` en `1` dans le fichier `Config.ini` (n'oubliez pas de relancer l'application après changement).



Changer la zone morte des joysticks pour drifter est supporté. Appuyez sur `ALT` + `F9` lorque l'application est au premier-plan, puis copiez/collez les valeurs dans le fichier `Config.ini` dans les paramètres `DeadZone` et redémarrez l'application.

## Touchpad
Jeux | Action
------------ | -------------
Uncharted 3: Drake’s Deception (2011) | Le bouton `Share` (ou `F12`) duplique l'appui gauche sur le touchpad.
The Last Of Us Part II (2020) | Options -> Accessibilité -> "Paramètres de gratte (guitar)" au lieu de vertical et horizontal, mettez boutons.

Sur la manette Xbox, vous devez appuyer sur le bouton `Retour/Vue/Select` (touchpad) et bouger le joystick dans le sens voulu pour simuler un toucher directionnel (ou glissé) sur le touchpad. Par défaut, l'appui sur le touchpad pendant le glissé est désactivé, vous pouvez l'activer dans le fichier de configuration en mettant `1` au paramètres `TouchPadPressedWhenSwiping`.



Vous pouvez aussi simuler le glissé via le clavier, les codes correspondant aux boutons sont décrits en dessous. 

## Gyroscope
1. Vérifiez le pare-feu Windows afin d'autoriser les connexions entrantes sur votre type de réseau (privé).
2. Installer FreePieIMU sur votre téléphone Android en prenant la dernière version ici [OpenTrack archive](https://github.com/opentrack/opentrack) ou ici [releases](https://github.com/r57zone/DualShock4-emulator/releases). 
3. Réduisez la sensibilité générale si nécessaire (le paramètre `Sens`, dans la section `Motion`, où `100` est une sensibilité de 100%) dans le fichier de configuration.
4. Réduisez la sensibilité du capteur individuel si nécessaire (les `AccelSens` et `GyroSense`, dans la section `Motion`, où `100` correspond à une sensibilité de 100 %) dans le fichier de configuration.
5. Inversez les axes si nécessaire (les paramètres `InverseX`, `InverseY` et `InverseZ`, dans la section `Motion`, où `1` active l'inversion et `0` désactive).
6. Modifiez l'orientation du téléphone (le paramètre `Orientation`, dans la section `Motion`, où `1` correspond au paysage et `0` au portrait).

Si vous avez just besoin de simuler une secousse de la manette (gyro) dans le jeu, dans ce cas il n'y a pas besoin d'installer l'application Android, appuyez sur le bouton `Shake` de la manette.

## Clavier et souris
Par défaut, le clavier/souris fonctionnent uniquement dans les fenêtres `PlayStation Plus` et `PS4 Remote Play` (changez le paramètre `ActivateOnlyInWindow2` si le nom de votre fenêtre est différent, pour les français, cela ne devrait pas). Pour fonctionner uniquement dans d'autres applications ou émulateurs, changez les paramètres `ActivateOnlyInWindow` et `ActivateOnlyInWindow2` pour qu'ils matchent le nom de vos applications (titre de la fenêtre principale). Vous pouvez aussi activer cette application pour qu'elle fenêtre dans toutes les fenêtres : changez le paramètre `ActivateAnyWindow` en `1` dans le fichier de configuration ou changez le paramètre `ActivateOnlyWindow` pour que la valeur soit le nom de la fenêtre voulue. Cela est nécessaire pour que le curseur soit centré uniquement dans une seule fenêtre et qu'aucun bouton ne soit appuyé si cette fenêtre est minimisée.

Pour désactiver le centrage du curseur, appuyez sur la touche `C` (possible de le changer dans le fichier de config -> `StopСenteringKey`).

Pour cacher le curseur après le démarrage de l'application, changez `HideCursorAfterStart` en `1`, pour le restaurer, fermez l'application via la croix ou `ALT` + `Echap`.

Pour le plein-écran, Playstation Plus utilise la combinaison de touches `ALT` + `F10` : la barre noire du haut et la barre des tâches sera masquée. Pour revenir à la fenêtre normale, appuyez sur ces touches de nouveau. Vous pouvez désactiver le masquage de la barre des tâches dans le fichier de configuratio en modifiant le paramètre `HideTaskBarInFullScreen` en `0`. Si la fenêtre Playstation Plus change une fois, vous pouvez modifier le décalage du haut par défaut : paramètre `FullScreenTopOffset`.


DualShock 4 | Souris/clavier
------------ | -------------
L1 | Alt
R1 | Control
L2 | Clic droit
R2 | Clic gauche
SHARE | F12
TOUCHPAD (appui) | Entrée
OPTIONS | Tab
HAUT | 1
GAUCHE | 2
DROITE | 3
BAS | 4
TRIANGLE | E
CARRÉ  | R
ROND | Q
CROIX | Espace
L3 (appui sur le joystick) | Shift
R3 (appui sur le joystick) | Bouton du milieu souris
Touchpad (glissé) ver le haut, bas, gauche, droite | 7, 8, 9, 0
Touchpad (clic) haut, centre, gauche, droite, bas  | U, J, H, K, N
Secouer la manette | T
Faites pivoter la manette de jeu vers l'avant, l'arrière, la droite, la gauche (gyroscope) | Pavé numérique 8, 2, 4, 6
PS | F2

Dans le fichier de configuration du profil, dans le dossier "Profiles", vous pouvez modifier les liaisons des boutons ou en créer un nouveau basé sur `Default.ini`. Les titres correspondants peuvent être trouvés [ici](https://github.com/r57zone/DualShock4-emulator/blob/master/BINDINGS.md). Vous pouvez choisir parmi des profils standards. Envoyez des fixations plus pratiques pour une variété de jeux.



Le paramètre de sensibilité `SensX`, `SensY` pour la souris mouse peut aussi être trouvé dans le fichier `Config.ini`, dans la section `Mouse`.
S'il n'y a pas de mouvement de joystick apparent, vous pouvez augmenter le paramètre `SleepTimeOut` en 2, 4, 8, 10.

Vous pouvez aussi activer l'émulation des boutons analogiques (L2, R2) : changez le paramètre `EmulateAnalogTriggers` en `1` and augmentez le `AnalogTriggerStep` (de 0.1 à 255).


## Téléchargement
>Version pour Windows 10.

**[Télécharger](https://github.com/r57zone/DualShock4-emulator/releases)**

## Feedback
`r57zone[at]gmail.com`
