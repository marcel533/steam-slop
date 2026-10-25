# Steam Slop: Run it / Starten

[English](#english) | [Deutsch](#deutsch)

---

<a id="english"></a>

# English

Needs Node.js 18.18 or newer (20 LTS recommended) and an internet connection.

## Linux (any distribution)

### 1. Install Node.js

With nvm (works on every distro, no root):

```bash
curl -fsSL -o /tmp/nvm-install.sh https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh
bash /tmp/nvm-install.sh
source ~/.bashrc
nvm install 20
nvm use 20
```

Or with your package manager (version may be older, check with `node -v`):

```bash
sudo apt install nodejs npm        # Debian, Ubuntu
sudo dnf install nodejs npm        # Fedora
sudo pacman -S nodejs npm          # Arch
```

### 2. Unpack and start

```bash
unzip steam-slop.zip
cd steam-slop
npm install
npm run dev
```

Open http://localhost:3000

### 3. Stop

Press `Ctrl+C` in the terminal. If it still runs in the background:

```bash
fuser -k 3000/tcp
```

## Windows

### 1. Install Node.js

Open PowerShell and run:

```powershell
winget install OpenJS.NodeJS.LTS
```

Or download the LTS installer from https://nodejs.org. Then close and reopen PowerShell and check:

```powershell
node -v
npm -v
```

### 2. Unpack and start

```powershell
Expand-Archive steam-slop.zip .
cd steam-slop
npm install
npm run dev
```

Open http://localhost:3000

If PowerShell says "running scripts is disabled":

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### 3. Stop

Press `Ctrl+C` in the terminal. If it still runs in the background:

```powershell
netstat -ano | findstr :3000
taskkill /PID <PID> /F
```

## Production mode (both systems)

```bash
npm run build
npm run start
```

---

<a id="deutsch"></a>

# Deutsch

Benötigt Node.js 18.18 oder neuer (20 LTS empfohlen) und eine Internetverbindung.

## Linux (jede Distribution)

### 1. Node.js installieren

Mit nvm (funktioniert auf jeder Distribution, ohne Root):

```bash
curl -fsSL -o /tmp/nvm-install.sh https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh
bash /tmp/nvm-install.sh
source ~/.bashrc
nvm install 20
nvm use 20
```

Oder mit dem Paketmanager (Version kann älter sein, prüfen mit `node -v`):

```bash
sudo apt install nodejs npm        # Debian, Ubuntu
sudo dnf install nodejs npm        # Fedora
sudo pacman -S nodejs npm          # Arch
```

### 2. Entpacken und starten

```bash
unzip steam-slop.zip
cd steam-slop
npm install
npm run dev
```

Öffnen: http://localhost:3000

### 3. Stoppen

`Ctrl+C` im Terminal. Läuft es noch im Hintergrund:

```bash
fuser -k 3000/tcp
```

## Windows

### 1. Node.js installieren

PowerShell öffnen und ausführen:

```powershell
winget install OpenJS.NodeJS.LTS
```

Oder den LTS-Installer von https://nodejs.org laden. Danach PowerShell schließen, neu öffnen und prüfen:

```powershell
node -v
npm -v
```

### 2. Entpacken und starten

```powershell
Expand-Archive steam-slop.zip .
cd steam-slop
npm install
npm run dev
```

Öffnen: http://localhost:3000

Meldet PowerShell "Skriptausführung ist deaktiviert":

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

### 3. Stoppen

`Ctrl+C` im Terminal. Läuft es noch im Hintergrund:

```powershell
netstat -ano | findstr :3000
taskkill /PID <PID> /F
```

## Produktionsmodus (beide Systeme)

```bash
npm run build
npm run start
```
