
# Jadx Setup (Ubuntu)

## Install Java

```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
```
## Verify:
```
java -version
```

## Download Jadx
```
wget https://github.com/skylot/jadx/releases/latest/download/jadx-1.5.5.zip
sudo apt install unzip -y
unzip jadx-1.5.5.zip
sudo mv jadx-1.5.5 /opt/jadx
```

Download Latest jadx

Go to the official GitHub page:

Jadx -> https://github.com/skylot/jadx

Or download directly using terminal:

wget https://github.com/skylot/jadx/releases/latest/download/jadx-1.5.0.zip

(If version changes, replace 1.5.0 with latest.)

## Add to PATH (ZSH Users)

```
nano ~/.zshrc
```
Add:
```
export PATH=$PATH:/opt/jadx/bin
```
Reload:
```
source ~/.zshrc
```

## Verify Installation
```
jadx --version
```

## Make Executable (IMPORTANT)

If you see permission denied:

```
sudo chmod +x /opt/jadx/bin/jadx
sudo chmod +x /opt/jadx/bin/jadx-gui
```
## Run GUI
```
jadx-gui "path/to/your.apk"
```

## CLI Mode (Creates folder output)
```
jadx yourapp.apk -d output_folder
```
### Common Problems
❌ command not found

Check PATH:
```
echo $PATH
```
❌ permission denied
```
sudo chmod +x /opt/jadx/bin/jadx
```





















