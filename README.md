# Streamer.bot Audio Emotes
<img style="width: 25%" src="AudioEmotes.png">

This Streamer.bot extension turns chat emotes that match keywords, into sounds on stream. The more emotes, the more sounds get played.

For example, clapping emotes can trigger the sound of applause, or laughing emotes can generate laughter.

## Installation

* Download [AudioEmotes.sb](https://raw.githubusercontent.com/WhazzItToYa/Streamerbot-AudioEmotes/refs/heads/main/AudioEmotes.sb) and [import it into Streamer.bot](https://docs.streamer.bot/guide/import-export#import) by dragging the downloaded file into the Streamer.bot Import window as usual.

The import includes a sample action that plays applause sounds for any emotes whose names contain "clap" or "applause".

## Setup

For each distinct category of emotes you want to play a type of sound for:

* Create a folder somewhere, and put sound clip files in it that you want played.
* Duplicate the included "Emote Applause (example)" into your own action.
* Edit the value of the "**Set Argument %soundFolder%**" to the path of the sound clip folder you created. The clips in this folder will be played randomly when the emotes are used.
* Edit the Value of the "**Set Argument %pattern%**" subaction to list all of keywords that should appear in the name of the emotes you want to play sounds for.  For example:
  * `clap,applause` would match any emotes containing the words "clap" or "applause", such as Clap, PeepoClap, or the Applause twemoji.
  * `lol,kekw,laugh,lul,giggle,lmao,rofl,kappa,hehe` matches all manner of laugh-related emotes.
* The default settings will ramp up the number & length of the sounds for each matching emote included in a chat message. You can adjust them by setting the following arguments:
  * `minRepetitions` : The number of sound clips that will be played for a single emote (default 1).
  * `maxRepetitions` : The most sound clips that will be played. Use this to keep your sounds from going crazy if someone was to spam emotes (default 32), or you set way too high a value for `exponentialMultiplier`.
  * `repsPerEmote` : The number of additional sound clips played for each additional matching emote in a message (i.e., linear growth)
  * `exponentMultiplier` : Controls how quickly the number of sound clips increase for each additional emote, in exponential growth. Values should generally stay somewhere between 0.0 & 1.0 Examples:
    * 0 : does not add any additional sounds per emote.
    * 1 : Doubles the number of clips played per emote.
    * 2 : Quadruples the number of clips played per emote


