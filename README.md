# Vaata AI

Нейросети для Vaata — просмотрщика и проявщика фото для Windows. Vaata скачивает их сама, когда они впервые
нужны (двинули ползунок «AI-шумодав» или открыли режим «Лицо»), проверяет каждый файл по SHA-256 и кладёт в папку
`ai` рядом с собой. Руками отсюда ничего брать не нужно.

## Что здесь

| Категория | Модель | Что делает | Лицензия | Размер | Релиз |
|---|---|---|---|---|---|
| denoise | [YOND gru32n](denoise/yond-gru32n) | шумодав RAW до дебайера | MIT | 22.4 МБ | [denoise-yond-gru32n-v1](https://github.com/arenshi/vaata-ai/releases/tag/denoise-yond-gru32n-v1) |
| faces | [YuNet](faces/yunet) | находит лица и пять точек на каждом | MIT | 231 КБ | [faces-yunet-v1](https://github.com/arenshi/vaata-ai/releases/tag/faces-yunet-v1) |
| faces | [EasyPortrait SegFormer-B0 512](faces/easyportrait-segformer-b0-512) | делит лицо на кожу, брови, глаза, губы и зубы | переработка CC BY-SA 4.0 от SberDevices, коммерческое использование разрешено | 15.3 МБ | [faces-easyportrait-segformer-b0-512-v1](https://github.com/arenshi/vaata-ai/releases/tag/faces-easyportrait-segformer-b0-512-v1) |

## Как устроено

- В git лежат только описания и лицензии, по папке на модель: `<категория>/<модель>/`.
- Файлы моделей — в релизах, по релизу на версию модели. Тег релиза — `<категория>-<модель>-<версия>`.
- [`catalog.json`](catalog.json) — все файлы с адресами, размерами и SHA-256. Тот же список вшит в Vaata, поэтому
  файл, подменённый на сервере, Vaata не примет.
- Сводка лицензий — [`LICENSES.md`](LICENSES.md).
- Среда выполнения (ONNX Runtime и DirectML из Windows ML, Microsoft) здесь не хранится: её лицензия не разрешает
  выкладывать её отдельно от приложения. Vaata берёт официальный пакет Microsoft с nuget.org — см.
  [`runtime/README.md`](runtime/README.md).

## Категории

- [`denoise`](denoise) — шумодавы RAW.
- [`faces`](faces) — лица: поиск и разбор на части.
