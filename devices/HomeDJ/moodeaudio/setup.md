# Moode Audio Setup for Streaming Local Podcasts, Music, and Tidal from NAS

This guide will walk you through the steps to set up Moode Audio on a Raspberry Pi to stream local media (music, audiobooks, podcasts, etc.) stored on a NAS. We will use **BubbleUPnP** as a UPnP/DLNA client to access the media from your NAS and stream it to Moode Audio.

## Prerequisites
- A Raspberry Pi running Moode Audio
- A **NAS** with UPnP/DLNA server enabled (if you have an attached media server)
- **BubbleUPnP (Android)** app for streaming

## Step 1: Set Up Moode Audio on Raspberry Pi
1. **Download and Flash Moode Audio**:
   - Download the latest Moode Audio image from [Moode's website](https://moodeaudio.org/).
   - Flash the image onto an SD card using balenaEtcher.
   - Insert the SD card into the Raspberry Pi and boot it up.

2. **Connect Raspberry Pi to Network**:
   - Connect the Raspberry Pi to your network via Ethernet or Wi-Fi.

3. **Access Moode Web Interface**:
   - Open a browser and go to `http://moode.local` or use the Pi’s IP address (e.g., `http://192.168.1.x`).

## Step 2: Enable UPnP/DLNA on Moode Audio
1. **Configure Moode for UPnP**:
   - In the Moode web interface, go to **Configure > Audio**.
   - Enable **UPnP/DLNA Renderer**.
   - Save the settings and reboot Moode if needed.

## Step 3: Set Up NAS for UPnP/DLNA (Optional)
If you have a media server (NAS), enable its UPnP/DLNA functionality:

1. **Enable UPnP/DLNA on Your NAS**:
   - For **Netgear NAS**: Refer to the user manual or Netgear's support website to enable UPnP/DLNA on your NAS.
   - Many NAS devices come with a built-in **media server** feature that enables UPnP/DLNA streaming.

2. **Add Your Music, Audiobooks, Podcasts, or Other Media to the NAS**:
   - Place your media files (e.g., music, audiobooks, podcasts, or other media) in a designated folder on your NAS for easy access.

   Example: If you're adding **podcasts**, create a folder named `Podcasts` on your NAS and store all your downloaded podcast episodes there for easy access through the UPnP server.

## Step 4: Set Up BubbleUPnP App (Android)
1. **Install BubbleUPnP** from [Google Play](https://play.google.com/store/apps/details?id=com.bubblesoft.android.bubbleupnp&hl=en&gl=US).
2. Open the app and go to **Settings > Media Servers**.
3. Select your NAS (it should show up as an available media server).
4. Go to **TIDAL** (or local library) and browse for your media.
5. **Link Tidal to BubbleUPnP** (Example for Streaming Tidal):
   - In the app, go to **Settings > TIDAL**.
   - Log in with your Tidal credentials to link the account.
   - Choose the audio quality (HiFi/Master) for optimal streaming.
6. **Select Moode as the Renderer**:
   - In the app, go to **Renderer** and select your Raspberry Pi (Moode device).
7. Play your media directly from the NAS or stream Tidal directly through BubbleUPnP.

## Step 5: Verify and Troubleshoot
1. **Check Moode Audio Playback**:
   - Ensure that Moode Audio is playing media through your NAS via the app.
   - If there are any issues, check the network connection or UPnP/DLNA settings.

2. **Verify Connection**:
   - Ensure both your Raspberry Pi and phone are on the same network.
   - Make sure the NAS is properly configured for UPnP/DLNA and accessible.

## Optional Enhancements
- **Download Podcasts Automatically**:
   - Use tools like **gPodder** or **FlexGet** to automate downloading podcasts to your NAS.
  
- **Use Moode Audio for Additional Features**:
   - Moode Audio can also stream music services like TIDAL, Spotify, and more. Customize your setup to include additional services as needed.

## Conclusion
By following these steps, you can stream your local media library from your NAS to Moode Audio using BubbleUPnP. Additionally, you can link your Tidal account for seamless lossless streaming (example shown). This setup provides a powerful, customizable way to enjoy podcasts, music, and audiobooks with high-quality audio playback.

---

Feel free to adjust the steps based on your specific setup or preferences.
