# Offline AI Dictation

Talk instead of type, on Android, without the internet. A floating button sits next to your keyboard in any app: tap it to dictate, hold it to get cleaned-up text. Speech recognition runs on your phone; nothing is sent anywhere unless you switch on an online option yourself.

Free and open source. A personal project by Naj, not for sale.

**Status: early (0.1.0).** Right now it works exactly like Phone Whisper 1.3.0, the app it's based on, under its own name so the two can be installed side by side. Coming next: offline AI cleanup, rewrite styles, a dictionary that learns your corrections, and a new setup and design. See [CHANGELOG.md](CHANGELOG.md).

## Based on Phone Whisper

Offline AI Dictation is a fork of [evilknivel/phone-whisper](https://github.com/evilknivel/phone-whisper) (version 1.3.0), which is itself a fork of [kafkasl/phone-whisper](https://github.com/kafkasl/phone-whisper), the original app by Pol Alvarez. It is not affiliated with or endorsed by either. Their credits are kept below.

## Credits

**Original author**
- **Pol Alvarez** ([@kafkasl](https://github.com/kafkasl)) created Phone Whisper: the idea, the floating push-to-talk button, insertion through the accessibility service, local transcription with sherpa-onnx, the model downloader, cleanup with prompt presets, the settings UI, the logo and the website. If the app saves you time, consider [sponsoring him](https://github.com/sponsors/kafkasl).

**Ideas from pull requests to the original repository**

None of these pull requests were merged here as code. We took their ideas and implemented them our own way; the authors deserve the credit for the ideas and for the problems they found.

| Contributor | Pull requests | What we took from them |
|---|---|---|
| **Renat** | [#8](https://github.com/kafkasl/phone-whisper/pull/8), [#9](https://github.com/kafkasl/phone-whisper/pull/9), [#10](https://github.com/kafkasl/phone-whisper/pull/10), [#11](https://github.com/kafkasl/phone-whisper/pull/11), [#12](https://github.com/kafkasl/phone-whisper/pull/12), [#13](https://github.com/kafkasl/phone-whisper/pull/13) | Show the button only while a keyboard is open; custom transcription API address; inserting without the clipboard; placeholder text in web editors; level meter and cancelling on screen off; retry state with readable error messages |
| **Maxime Borges** | [#19](https://github.com/kafkasl/phone-whisper/pull/19)–[#25](https://github.com/kafkasl/phone-whisper/pull/25) | Direct per-file downloads from Hugging Face instead of slow bz2 archives; downloads in a foreground service; the finding that sherpa-onnx's Whisper default translates into English; correct model sizes; inserting directly while a keyboard is open, and Telegram's placeholder reported as text |
| **ArtificialTruth** | [#16](https://github.com/kafkasl/phone-whisper/pull/16) | Releasing the local model after inactivity and loading it again on demand |
| **Luc Brinkman** ([@lucbrinkman](https://github.com/lucbrinkman)) | [#14](https://github.com/kafkasl/phone-whisper/pull/14) | Proposed an open-source license; the original repository is licensed under Apache 2.0 |

**This fork: evilknivel** ([@evilknivel](https://github.com/evilknivel)), implemented with [Claude Code](https://claude.ai/code). Every idea in this fork that is not credited above comes from evilknivel, among them:
- OpenRouter and custom servers as providers, the live model pickers, separate providers for transcription and cleanup
- Parakeet Ultra and the multilingual Whisper models, the language setting, cleanup that never translates
- the setup assistant, the status line that names what is missing, the settings split into sub-pages, protected API key input
- hold to dictate with AI cleanup, the hold ring in the color of the mode, distinct vibrations, the glowing screen edge, messages above the thumb, the ✕ to discard
- translation by sliding onto a language on the arc, offline English translation with Whisper, the + and ⚙ shortcuts and the Quick Settings tile
- the English and German documentation and the 1.x releases

**Software and models used**

| Component | Author | License |
|---|---|---|
| [sherpa-onnx](https://github.com/k2-fsa/sherpa-onnx) (speech recognition runtime, Kotlin API) | k2-fsa / Next-gen Kaldi | Apache 2.0 |
| [Silero VAD](https://github.com/snakers4/silero-vad) (bundled, silence trimming) | Silero Team | MIT |
| Parakeet 110M, Parakeet 0.6B v3 | NVIDIA | CC BY 4.0 |
| [Parakeet Ultra](https://huggingface.co/moondream/parakeet-ultra) | Moondream (based on NVIDIA Parakeet) | CC BY 4.0 |
| [Parakeet Ultra int8 for sherpa-onnx](https://huggingface.co/mldecode/parakeet-ultra-onnx-int8) | mldecode | CC BY 4.0 |
| Whisper Base, Whisper Small | OpenAI | Apache 2.0 (model weights), MIT (code) |
| Moonshine Tiny | Useful Sensors | MIT |
| sherpa-onnx model conversions on Hugging Face | Fangjun Kuang ([csukuangfj](https://huggingface.co/csukuangfj)) | as the original models |
| OkHttp, AndroidX, Material Components, Apache Commons Compress | Square, Google, Apache Software Foundation | Apache 2.0 |

The models are downloaded from their publishers at your request and are not part of this repository.

## License

Apache License 2.0, see [LICENSE](LICENSE). Copyright of the original code: Pol Alvarez. The names "Phone Whisper" and the logo belong to the original author; the Apache license does not grant trademark rights.


Changes made in this fork are listed in [CHANGELOG.md](CHANGELOG.md) under the Offline AI Dictation versions.
