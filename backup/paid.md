# Paid tools comparison

quality vs cost vs speed vs time to implement vs failure rate (to achieve quality) vs customizability vs api availability

## Text

### [Leaderboard](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard)

| Provider                                                    | Model               | Price                                                                                                              |
| ----------------------------------------------------------- | ------------------- | ------------------------------------------------------------------------------------------------------------------ |
| OpenAI (Overall Choice)                                     | 4o mini             | $0.75/2M tokens                                                                                                    |
| [OpenRouter](https://openrouter.ai/models?order=top-weekly) | Various             | Free versions available                                                                                            |
| Gemini                                                      | 1.5 Flash           | $0.375/2M tokens (2000 pages context window, 1M tokens = 500k words @ 2 tokens/word = 2000 pages @ 250 words/page) |
| Claude                                                      | 3.5.sonnet beta     | Very costly                                                                                                        |
| Cohere                                                      | Command R           | -                                                                                                                  |
| Llama (Open Source Choice)                                  | 3.1 70B/8B instruct | -                                                                                                                  |
| Mistral                                                     | Nemo                | -                                                                                                                  |

## Audio

### [Leaderboard](https://huggingface.co/spaces/TTS-AGI/TTS-Arena)

### Voice (Rs 25.4 / 10min)

avg talking speed: 150 words/min
avg chars per word: 5
chars per min: 750

| Provider                                         | Price             | Notes                                                            |
| ------------------------------------------------ | ----------------- | ---------------------------------------------------------------- |
| [murf.ai](https://murf.ai) (Current Choice)      | $0.03/min         | 26min free monthly                                               |
| [elevenlabs](https://elevenlabs.io)              | $0.11/min         | 26min free monthly (non-commercial), 10min speech-to-speech free |
| [play.ht](https://play.ht)                       | $0.15/min         | -                                                                |
| [dubverse](https://dubverse.ai)                  | $0.15/min (Rs 12) | Marathi language support                                         |
| [naturalreaders.com](https://naturalreaders.com) | -                 | -                                                                |
| [ttsmaker.com](https://ttsmaker.com)             | Free              | Free download                                                    |

### Music (Rs 25.5 / song)

| Provider                                                                             | Price                     | Notes                              |
| ------------------------------------------------------------------------------------ | ------------------------- | ---------------------------------- |
| [soundraw](https://discover.soundraw.io/api)                                         | $0.3/song (Rs 25.41/song) | API available                      |
| [music.ai](https://music.ai/pricing/?utm_source=direct&click_section=header_pricing) | -                         | Most advanced music AI integration |
| suno                                                                                 | $10/250 songs             | No official API, 10 free songs/day |
| udio                                                                                 | -                         | -                                  |
| aimusic.so                                                                           | Free                      | Online only                        |
| brev.ai                                                                              | Free                      | -                                  |
| ilovesong.ai                                                                         | Free                      | -                                  |
| beatoven.ai                                                                          | $200/1hr music            | API available, or 10 videos        |
| loudly.com                                                                           | $8/900 tracks             | API available, 15 free tracks/day  |

## Image

### [Paid Leaderboard](https://huggingface.co/spaces/ArtificialAnalysis/Text-to-Image-Leaderboard)

### [Open Source Leaderboard](https://huggingface.co/spaces/TIGER-Lab/GenAI-Arena)

### Text to Image (Rs 3.5)

| Provider     | Model              | Price        | Notes                                                |
| ------------ | ------------------ | ------------ | ---------------------------------------------------- |
| Recraft      | v3                 | $0.12/image  | Includes style + upscale, base $0.04/image (Rs 3.39) |
| Flux         | 1.1 Pro            | $0.04/image  | Rs 3.39/image                                        |
| Midjourney   | 6.1                | -            | No official API                                      |
| Ideogram     | v2                 | $0.08/image  | -                                                    |
| Stability AI | SD 3.5 Large Turbo | $0.04/image  | -                                                    |
| Flux         | 1 Shnell           | $0.003/image | -                                                    |

### Apparel Fashion specific (Rs 12)

| Provider                                                                      | Price                       | Notes              |
| ----------------------------------------------------------------------------- | --------------------------- | ------------------ |
| [kolors by kling](https://www.appypie.com/endpoint/virtual-try-on/kolors-api) | $0.14/image (Rs 11.9/image) | $49/350 API calls  |
| [pixelcut](https://www.pixelcut.ai/api/try-on)                                | $0.1/image (Rs 8/image)     | -                  |
| [fashn ai](https://fashn.ai/products/api)                                     | $0.04/image (Rs 3.39/image) | -                  |
| idm-vton                                                                      | $0.036/image (Rs 3/image)   | Open source        |
| [appypie](https://www.appypie.com/endpoint/pricing-plan)                      | -                           | 1000 API calls/$19 |
| vue.ai                                                                        | -                           | -                  |

## Video

### Leaderboards

-   [Paid Leaderboard](https://huggingface.co/spaces/ArtificialAnalysis/Video-Generation-Arena-Leaderboard)
-   [HuggingFace Trending](https://huggingface.co/models?pipeline_tag=text-to-video&sort=trending)
-   [HuggingFace Image-to-Video Models](https://huggingface.co/models?pipeline_tag=image-to-video&sort=trending)
-   [Awesome Video Diffusion Models](https://github.com/showlab/Awesome-Video-Diffusion?tab=readme-ov-file#open-source-toolboxes-and-foundation-models)

### Text to Video (Rs 23/min, Rs 162.6/min, Rs 508/min)

| Provider                                                  | Model | Price        | Notes                       |
| --------------------------------------------------------- | ----- | ------------ | --------------------------- |
| [minimax](https://replicate.com/minimax/video-01)         | -     | Rs 508/min   | $0.5/5 sec                  |
| [hunyuanvideo](https://github.com/Tencent/HunyuanVideo)   | -     | $8.28/min    | 80GB model, $0.69/5 sec     |
| mochi                                                     | 1     | -            | $0.35/5 sec                 |
| runway                                                    | -     | -            | $0.25/5 sec                 |
| [kling](https://piapi.ai/kling-api)                       | -     | Rs 162.6/min | Unofficial API, $0.16/5 sec |
| [luma ray](https://lumalabs.ai/dream-machine/api/pricing) | -     | -            | $0.4/5 sec 720p             |
| [haiper](https://haiper.ai/enterprise-api)                | 2.0   | Rs 254/min   | $0.05/sec 720p              |
| pika                                                      | 1.5   | -            | Ask for API                 |
| [ltx video](https://replicate.com/fofr/ltx-video)         | -     | Rs 23.72/min | $0.014/3 sec                |
| [pyramid flow](https://replicate.com/zsxkib/pyramid-flow) | -     | Rs 447.2/min | $0.44/5 sec                 |
| [cogvideox](https://replicate.com/cuuupid/cogvideox-5b)   | 5B    | Rs 491.2/min | $0.58/6 sec                 |

### Apparel Fashion specific (no proper video available)

| Provider                                                                            | Model | Price      | Notes        |
| ----------------------------------------------------------------------------------- | ----- | ---------- | ------------ |
| [thenewblack](https://thenewblack.ai/ai-design-features/ai-fashion-video-generator) | -     | $1.5/5 sec | Rs 127/5 sec |

### Ads

| Provider                                     | Model | Price        | Notes                        |
| -------------------------------------------- | ----- | ------------ | ---------------------------- |
| [creatify](https://creatify.ai/)             | -     | $0.104/video | 480 videos/$50, 2 free/month |
| [arcads](https://www.arcads.ai/ai-video-api) | -     | $10/video    | -                            |
