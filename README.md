Micheline
===

Micheline is your personnal assistant for everyday.

Call her with "Ok Micheline" and ask her what you like.

It consist of a Language interpretation module, ChatGPT and a Voice bot.

Credit to Micode [original project](https://github.com/michael-dm/eva) from [Underscore_](https://www.youtube.com/watch?v=_1uN7o1PpZo). A huge thanks !


Why Micheline ?
---
Because Micode triggers it with "Ok Michel", because I find this name funny and mostly because of an inside joke with old friends. _Team Micheline !!!_


# Install developer environment
git clone https://github.com/pumbaa666/Micheline.git
cd Micheline
npm i

mkdir bin && cd bin
git submodule add https://github.com/chirlu/sox.git
git submodule add https://github.com/ggerganov/whisper.cpp.git
cd whisper.cpp/models
git submodule add https://huggingface.co/bofenghuang/whisper-medium-cv11-french

npm run postinstall
<!-- npm run rebuild-speech-recorder
npm run generate
npm run build
npm run preview -->
npm run dev



# Electron Assistant



https://github.com/michael-dm/eva/assets/26444186/9d0b307b-37bf-4abf-8798-84f6e6f7a9a4



Boilerplate of whisper.cpp + chatGPT + Electron.
Goal is low latency.

Could be extended in many ways :
- add voice output with elevenlabs/Bark
- get text selection as input
- get file selection as input
- use OpenAI functions to execute "tools"
- save "memories" into Prisma db

e.g. : "convert this mov to wav please"

## Instructions

- Expose OPENAI_API_KEY env variable in your shell
- create `bin` folder in root directory and add required binaries :
  - whisper -> main program from whisper.cpp
  - sox
  - at least one ggml whisper model (I use quantized french fine-tunes from [here](https://huggingface.co/bofenghuang/whisper-medium-cv11-french/tree/main))
- [Mac M1 binaries](https://www.dropbox.com/sh/ncxavljogsb6xch/AACzK0t2zWpZTT0EahDWDz-0a?dl=0) at your own risk
- Expect many bugs and hacks
- `pnpm i`
- `pnpm dev`
