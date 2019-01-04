### Installation

```
sudo apt-get install python-pyaudio python3-pyaudio

sudo pip3 install speechrecognition
```

### Give it a try

```
python3 -m speech_recognition
```

### Let's go

```
import speech_recognition as sr

r = sr.Recognizer()
mic = sr.Microphone()

def get_text(wav_bytes):
    result = here_is_a_function_which_take_voice_then_return_text(wav_bytes)
    return result

while 1:
    print("\nPlease try to speak something...")
    with mic as source:
        r.adjust_for_ambient_noise(source)
        audio = r.listen(source)
        audio_data = audio.get_wav_data(convert_rate=16000)
        print("\nGot you, now I'm trying to recognize that...")
        text = get_text(audio_data)
        print(f"\n{text}")
```

### links may helpful

https://realpython.com/python-speech-recognition/