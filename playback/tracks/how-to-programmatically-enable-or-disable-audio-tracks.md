# How to programmatically enable or disable audio tracks
This article describes how you can use the MediaTrack API to enable or disable audio tracks.
The AudioTrack API, which is a sub-API of the MediaTrack API, can be used to implement this functionality. 
Implementing this functionality is a common use-case for developers who want to build their own UI to toggle audio languages on and off.

## Using the AudioTrack API to enable different tracks
As mentioned above, you can use the AudioTrack API to enable or disable an audio track. Once you've programmatically selected a track, you can use its enabled property (or method) and set it to true or false.

## Code examples
The code examples below show how to implement toggling audio tracks. It's advised to disable audio tracks which you don't want to play, in order to avoid issues with overlapping audio.

Web SDK
```js
// disable all audio tracks
player.audioTracks.forEach(function(track) {
    track.enabled = false;
});
// enable a specific audio track
player.audioTracks[indexOfRequestedAudioTrack].enabled = true;
```

Android (TV) SDK
```java
// disable all audio tracks
for (int i = 0; i < theoplayer.getPlayer().getAudioTracks().length(); i++) {
    theoplayer.getPlayer().getAudioTracks().getItem(i).setEnabled(false);
}
// enable a specific audio track
theoplayer.getPlayer().getAudioTracks().getItem(i).setEnabled(true);
```

iOS (/tvOS) SDK
```swift
// disable all audio tracks
for i in 0..<self.player.audioTracks.count {
    var audio = self.player.audioTracks.get(i)
    audio.enabled = true
}
// enable a specific audio track
    var desiredAudio = self.player.audioTracks[indexOfRequestedAudioTrack]
    desiredAudio.enabled = true
```

