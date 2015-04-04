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

# Using CMU PocketSphinx on Ubuntu Trusty 14.04 provisoned using Vagrant

1. git clone https://github.com/cmusphinx/sphinxbase.git
2. git clone https://github.com/cmusphinx/pocketsphinx.git
3. Install the above with required packages and libraries
4. If pocketphinx is correctly installed, run:
    pocketsphinx_continuous -infile /vagrant/numbers.wav > numbers_without_hmm.txt
5. The Input data file numbers.wav was generated thus:

  a. Enter a youtube url in http://www.youtube-mp3.org/ to get the mp3.
  
  b. Using Audacity convert the generated mp3 from step ( a)to .wav file with these properties
  
    * Load the file and then select "Split track from the menu" for Single mono channel
    * Select Project rate of 16,000 Hz.
    * From file menu, select Export selected audio and save it as 16-bit PCM wav format file 'numbers.wav'

As, seen in step 4, above the transcription is captured in the output file 'numbers_without_hmm.txt'
