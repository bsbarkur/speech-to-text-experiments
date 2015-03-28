# speech-to-text-experiments

A repository that contains my speech to text experiments.

# Using Google's Speech API V2

1. Install Audacity from http://audacity.sourceforge.net/

2. Record a voice sample in Audacity and save it as FLAC type

3. Enable your API acess for Google speech API using instructions given here:
http://stackoverflow.com/questions/26485531/google-speech-api-v2

4. Run this command to post to Google's servers to let them do the automatic speech recognition
curl -X POST --data-binary @NAME_OF_YOUR_FILE.flac --header 'Content-Type: audio/x-flac; rate=44100;' 'https://www.google.com/speech-api/v2/recognize?output=json&lang=en-us&key=SPEECH_API_KEY&maxresults=1'

5. Output json for test.flac in the audio-examples folder
{"result":[]}
{"result":[{"alternative":[{"transcript":"i am from india"}],"final":true}],"result_index":0}

It correctly recognizes for this sample!



