# GiroBall ⚽

<img width="400" height="723" alt="GiroBall" src="https://github.com/user-attachments/assets/bbc9b91f-0bb0-40a0-80fa-e1c7ffe6a371" />


## How it works

GiroBall is a two-player browser game built as a single HTML file. **Three.js** renders the 3D field, **cannon-es** simulates the balls, and **Trystero** uses Nostr relays to help the browsers find each other before establishing a **WebRTC** connection. The room creator runs the match physics and goal detection; the guest sends controls and receives the game state.

Room codes can be shared in two ways: type the five-character code, or **send it through sound**. The host taps **Emit**, which plays a short sequence of tones through the phone speaker. The guest's microphone listens, decodes the tones, checks the code, and joins the room. This audio handshake uses the **Web Audio API**; it is an alternative to typing the code, not the connection that carries gameplay.

**Play online:** [joaocarvalhofelix.github.io/GiroBall](https://joaocarvalhofelix.github.io/GiroBall/)

## Play

1. Open the game in a browser on each phone. Allow motion sensor access if prompted.
2. On one phone, select **Create room** and share the room code.
3. On the other, select **Join room** and enter the code. To use sound, put the phones near each other and tap **Emit** on the host. The guest starts listening automatically on the join screen; **Listen** also lets you stop or restart listening.
4. Once connected, tilt your phone to steer your ball. Move the white football into your opponent's goal.

Touch anywhere on the open field to charge a kick, then **release to shoot**. A quick tap gives a small nudge; holding longer makes the ball compress and produces a stronger kick. Kicks have a cooldown and use energy that recovers over time. Use **Calibrate** if your ball moves while the phone is still. **Menu** returns to the main menu.

**Solo training** offers four modes: **Follow the line**, **Dribbling**, **Aiming**, and **Free practice**.

## Connection notes

The phones do **not** need to be on the same network. Some mobile networks, routers, and operators can still prevent the WebRTC connection from forming. Connected Nostr relays mean room discovery is available; they do not guarantee that the two browsers can establish a peer connection.

If a match does not start:

- Check that both phones have the same game version and that the host is still in the room.
- Check the code or send it again through sound.
- Try another network or Wi-Fi connection if WebRTC fails.
- Use **Copy diagnostics** on the room screen to capture connection details.
