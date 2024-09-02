# Aplikace-AI-pro-zpracovani-obrazu

Uživatelský účet: *jetson*

Heslo: *prozradím*

## Zprovoznění systému NVIDIA Jetson Orin Nano

### Základní příkazy Linuxu
Popis základních příkazů pro systém Linux.

**`ls`**  
Zobrazuje seznam souborů a adresářů v aktuálním adresáři.

**`cd`**  
Změní aktuální pracovní adresář.

**`pwd`**  
Vypíše aktuální pracovní adresář.

**`mkdir`**  
Vytvoří nový adresář.

**`rmdir`**  
Smaže prázdný adresář.

**`rm`**  
Smaže soubor nebo adresář (s použitím přepínače `-r` pro adresáře).

**`cp`**  
Kopíruje soubor nebo adresář na nové místo.

**`mv`**  
Přesune nebo přejmenuje soubor nebo adresář.

**`touch`**  
Vytvoří nový prázdný soubor nebo aktualizuje časovou známku existujícího souboru.

**`cat`**  
Vypíše obsah souboru do terminálu.

**`echo`**  
Vypíše text nebo proměnnou do terminálu.

**`man`**  
Zobrazí manuálovou stránku pro zadaný příkaz.

**`chmod`**  
Změní oprávnění souboru nebo adresáře.

**`chown`**  
Změní vlastníka souboru nebo adresáře.

**`apt`**  
Spravuje balíčky (instalace, aktualizace, odstranění) na Debian-based systémech.

**`sudo`**  
Umožní spustit příkaz s administrátorskými (root) právy.

**`find`**  
Vyhledává soubory a adresáře podle jména nebo jiných kritérií.

**`grep`**  
Hledá specifický text nebo vzorek v souborech.

**`df`**  
Zobrazuje informace o využití disku.

**`du`**  
Zobrazuje využití místa v adresáři.

**`ps`**  
Zobrazuje seznam aktuálně běžících procesů.

### Instalace některého softwaru a zprovoznění

#### Instalace Firefoxu 

`sudo apt-get install firefox` (Pokud chcete jiný prohlížeč, modifikujte)

#### Instalace Visual Studio Code

Nastavení místa pro stžení balíku `cd Downloads `

Aktualizace balíku v cache: 

`sudo apt update`

`sudo apt upgrade`

Stažení balíku s *vscode*

`wget -N -O vscode-linux-deb.arm64.deb https://update.code.visualstudio.com/latest/linux-deb-arm64/stable`

Vlastní instalace balíku

`sudo apt install ./vscode-linux-deb.arm64.deb`

+Spuštění vscode

#### Připojení pomocí ssh

Nejprve zjistíme lokální IP adresu zařízení: `ip addr show` nebo `ifconfig` (na jetsonu)

Pro připojení použijeme program*ssh* `ssh jetson@x.x.x.x` (na osobním počítači)
Možno vyzkoušet forwardování X serveru, přepínač -X.

#### Ověření funkčnosti kamery 

viz https://www.waveshare.com/wiki/Jetson_Orin_Nano#Overview

Pro jednu kameru spustíme následující příkaz:
`gst-launch-1.0 nvarguscamerasrc sensor-id=0 ! "video/x-raw(memory:NVMM), width=(int)1920, height=(int)1080,format=(string)NV12, framerate=(fraction)30/1" ! nvvidconv ! xvimagesink sync=false`

