# C# .NET Core + Visual Studio Code + GitHub beállítása

## Fejlesztői környezet telepítése, beállítása
1.  .NET Core SDK telepítése<br>
    https://microsoft.com/net/core
2.  Git for windows telepítése (opcionális, git-hez):<br>
    https://git-for-windows.github.io/
3.  Visual Studio Code (továbbiakban VSCode) telepítése:<br>
    https://code.visualstudio.com/docs/setup/setup-overview
4.  VSCode futtatása, Visual Studio Extensions telepítése: Ctrl-Shift-X<br>
    Kiterjesztés keresése, telepítés:
    - C# for Visual Studio Code (powered by OmniSharp)<br>
       https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp
    - vscode-pfd (PDF fájlok betöltéséhez)
    (opcionális: további kiterjesztések telepítése igény szerint)
5.  Billentyűkombinációk beállítása: 
    File\Preferences\Keyboard Shortcuts menüvel, vagy Ctrl-K majd Ctrl-S<br>
    Parancs keresése: gépeléssel<br>
    Hozzárendelés, módosítás: "ceruza" ikonra kattíntással, törlés: Del bill.<br>
     - gépel: "delete" > parancs: "Delete Line" > hozzárendel: Ctrl-L
     - opcionális: további billentyűkombinációk hozzárendelése tetszés szerint
6.  Opcionális: VSCode beállítása: lsd. az oldal végén

## Projekt előkészítése (inicializálása)
1. Projekt mappa létrehozása (pl.: JedlikCsharpTemplate)
2. CMD.EXE (Parancssor futtatása)
3. Projekt mappa aktuálissá tétele (pl.: CD JedlikCsharpTemplate)
4. "dotnet new console" parancs futtatása (idézőjelek nélkül)
5. VSCode indítása, projekt mappa megnyitása (File\Open Folder...)<br>
   (az első indításkor hosszabban telepít két komponenst)
6. Warn: Required assets to build and debug are missing<br>
   from 'JedlikCsharpTemplate'. Add them?<br>
   "Yes" -> .vscode/launch.json + tasks.json létrejön
7. launch.json szerkesztése:
   - "console": "internalConsole", ->  Belső console ablak, Console.ReadLine() NEM működik
   - "console": "integratedTerminal", -> Belső terminál ablak, Console.ReadLine() működik
   - "console": "externalTerminal", -> Külső console ablak, Console.ReadLine() működik
8. .gitignore fájl hozzáadása a projekt főkönyvtátába (opcionális):
   "bin" tartalommal (idézőjelek nélkül, nem tölti fel a mappát GitHub-ra)

## Fejlesztés, tesztelés
1.  VSCode indítása (utoljára megnyitott projektet visszatölti), vagy<br>
    Project mappa helyi menüből: Open with Code, vagy<br>
    VSCode indítása után File/Open Folder... menüpontba a project mappa megnyitása
2.  Program.cs szerkesztése (át is lehet nevezni)
3.  Futtatás, nyomkövetés: F5-el<br>
    https://docs.microsoft.com/hu-hu/dotnet/core/tutorials/with-visual-studio-code#debug

## Hasznos linkek:
- https://code.visualstudio.com/docs
- https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf
- https://github.com/Microsoft/vscode-tips-and-tricks
- https://git-scm.com/book/en/v2
- https://help.github.com/articles/basic-writing-and-formatting-syntax/

## Verziókezelés Git-el VS Code-ban (nagyon alap, opcionális):
1. Github account létrehozása:<br>
   https://github.com/<br>
   (nitslaszlo az account név a példában)
2. Git repository létrehozása:<br>
   pl.: GitHub asztali alkalmazással vagy github.com-on<br>
   (JedlikCsharpTemplate a repository neve a példában)
3. Git konfigurálása Git CMD ablakból (1x kell csak, Windows megjegyzi):<br>
   git config --global user.name nitslaszlo@gmail.com<br>
   git config --global credential.helper wincred
4. Visual Studio Code indítása - project betöltése
5. ".gitignore" fájl létrehozása project főkönyvtárban (opcionális):<br>
    Ctrl-N -el új fájl létrehozása<br>
    A fájl tartalma:<br>
    bin<br>
    (További mappák és fájlok megadhatóak, melyek nem kerülnek "feltöltésre")<br>
    Ctrl-S -> mentés
5. Git inicializálása a 3. ("Y") ikonnal vagy Ctrl-Shift-G<br>
   majd "Initialize Repository"-ra kattint (felül)
6. Ctrl-Shift-G -> Commit message megadása, majd commit Ctrl-Enter -el
7. Remote repository megadása új terminál ablakból (Ctr-Shift-ö)
   - "git remote add origin https://github.com/nitslaszlo/JedlikCsharpTemplate.git"
   - "git push -u origin master"

### Fel/le töltés GitHub-ra későbbiekben:
1. Ctrl-Shift-G -> Commit message megadása, majd commit Ctrl-Enter -el
2. Változások szinkronizálása ("feltöltés")<br>
   Alul a státus sorban balra "Synchronize Changes" -ra kattínt

## VS Code editor beállítása:
1. Ctrl-Shift-P vagy F1
2. "Preferen..." gépelése
3. Preferences: "Open Workplace Settings" a projektben tárolt beállításokhoz (ez az erősebb) vagy
4. Preferences: "Open User Settings" a felasználónált tárolt beállításokhoz<br>
   Konfig fájl workspace: projekt/.vscode/settings.json<br>
   Konfig fájl user: c:/Users/UserName/AppData/Roaming/Code/User/settings.json





