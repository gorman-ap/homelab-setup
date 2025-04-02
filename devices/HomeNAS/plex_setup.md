# Installing Plex on an Unsupported NAS


Because Plex is no longer officially supported on this NAS model, manual installation was required:

## 1. Download the Plex Package
- Go to the Plex Downloads page.
Choose the correct ARM-based Linux NAS package compatible with your device (e.g., ReadyNAS ARM).
- This specific model is running [ReadyNas OS](https://kb.netgear.com/000065653/ReadyNAS-OS-Software-Version-6-10-9)

## 2. Transfer to the NAS
- Ensure the NAS has FTP service enabled (usually via its admin web interface).
- On your workstation (e.g., HomeServ or Voyager), use an FTP client or CLI tool:

- Example with ftp CLI:
```bash
ftp <NAS-IP>
# Login with your NAS credentials
put plexmediaserver_<version>.deb
quit
```
## 3. Install via SSH

- SSH into the NAS:
```bash
ssh <admin>@<NAS-IP>
```

- Navigate to the directory where the .deb file was uploaded:

```bash
cd /path/to/uploaded/file
```
- Install the package manually:
```
sudo dpkg -i plexmediaserver_*.deb
```

## 3. Install via SSH
- SSH into the NAS using administrative credentials.
- Navigate to the directory containing the uploaded package.

- Run the installer manually:

```bash
Copy
Edit
sudo dpkg -i plexmediaserver_*.deb
```

## 4. Start Plex
Plex should auto-start or appear in the NAS service list.

- Access Plex via:
http://<NAS-IP>:32400/web

# Future Updates
- This installation method may need to be repeated when new Plex versions are released.
Automatic updates are not guaranteed on unsupported NAS hardware.

### Keep backups of working installers in case newer versions drop support entirely.
