# Анимированное демо Mini Product Creator

26 секунд, 1280×720, без звука. Пример сценария интервью и создания продукта, а не запись отдельного SaaS.

```sh
npm run dev
npm run check
npm run render -- --fps 30 --quality delivery --output ../../assets/mini-product-creator-demo.mp4
```

HyperFrames 0.8.181 закреплён в package.json. Исходник композиции — index.html; дизайн и ход сцены — frame.md и STORYBOARD.md. GIF в README репозитория получена из финального MP4, loop включён.

Шрифты Manrope и PT Serif из Google Fonts распространяются по OFL; лицензии лежат в public/fonts/. GSAP 3.14.2 размещён локально с сохранённым заголовком лицензии. Базовые примитивы chat-message и typing-indicator установлены из реестра HyperFrames и адаптированы для композиции.

GIF для README воспроизводится автоматически и зациклена. Команда из папки assets репозитория:

```sh
ffmpeg -ss 1.1 -i mini-product-creator-demo.mp4 -filter_complex '[0:v]fps=12,scale=960:-1:flags=lanczos,split[s0][s1];[s0]palettegen=max_colors=128:stats_mode=diff:reserve_transparent=0[p];[s1][p]paletteuse=dither=bayer:bayer_scale=4:diff_mode=rectangle' -loop 0 mini-product-creator-demo.gif
```

Фактические проверки: [QA.md](QA.md).
