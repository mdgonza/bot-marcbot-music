# Basic Discord Music Bot

This app allows you to play audio tracks in a Discord voice channel
of your choice:

<img src="./readme/gallery/1-play-track.png" style="max-width: 60%">

It also contains a simple system for queueing tracks in advance:

<img src="./readme/gallery/2-enqueue-track.png" style="max-width: 60%">

You can search for tracks or enter a direct YouTube link!

# Setup

The only required setup is to get the id of a voice channel you would like to
designate as your server's "radio channel". You can find this id by right
clicking a voice channel in your server with developer mode enabled:

<img src="./readme/gallery/4-copy-voice-channel-id.png" style="max-width: 60%">

If you need help enabling developer mode, [see this section of the official guide](https://autocode.com/guides/how-to-build-a-discord-bot/#faq-1).

As of August 31st 2022, Discord restricts your bot’s ability to see when messages are sent by server members. This means that you’ll be unable to use event triggers such as `message.create`, `message.create.prefix` and `bot_mention` without enabling the **Message Content Intent**.

To enable this intent, head over to the [Discord Developer Portal](https://discord.com/developers/applications), click your bot’s name, then click the *Bot* button on the sidebar. Scroll down, and you’ll see a switch to turn on the Message Content Intent. If you get stuck, [check out this guide for screenshots showing what to click](https://autocode.com/discord/threads/what-are-discord-privileged-intents-and-how-do-i-enable-them-tutorial-0c3f9977/).

If your bot is in over one hundred servers, you’ll need to complete Discord’s [intent whitelisting process](https://support.discord.com/hc/en-us/articles/360040720412-Bot-Verification-and-Data-Whitelisting) to enable the Message Content Intent.

# Prefix Commands 

- `!play <query>`: Play or search for a track
- `!play` Resume a paused track or play the latest track from the queue if the player is disconnected
- `!pause`: Pause the currently playing track
- `!disconnect`: Disconnect the bot from the voice channel
- `!queue`: Retrieve the current track and queued tracks
- `!enqueue <query>`: Add a track to the queue
- `!skip`: Skip currently playing track and play the next track in the queue
- `!clearqueue`: Clear the current queue
- `!help`: Bring up help menu

Queued tracks automatically play when the last track finishes.

# Troubleshooting

This app uses the [ytdl-core](https://github.com/fent/node-ytdl-core) npm package
to stream from YouTube, which is frequently updated as YouTube makes changes. 
If your bot has issues downloading a particular track, try again later or check 
for an updated version of the dependency.

# Thank You!

If you have any questions or feedback, please join our community Discord 
from the Community tab in the top bar. You can also follow us on Twitter, 
[@Autocode](https://twitter.com/Autocode).
