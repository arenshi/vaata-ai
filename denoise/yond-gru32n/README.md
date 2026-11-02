# YOND gru32n — AI-шумодав

Сеть из работы «You Only Need a Denoiser» (Hansen Feng и соавторы), вариант GuidedResUnet `gru32n`, обученный
убирать гауссов шум. Vaata подаёт ей RAW до дебайера — четыре плоскости матрицы Байера после преобразования
Анскомба — и возвращает очищенные плоскости в проявку.

| | |
|---|---|
| Источник кода и весов | <https://huggingface.co/spaces/hansen97/YOND> |
| Лицензия | MIT — файл [`LICENSE`](LICENSE) (Copyright (c) 2025 fenghansen) |
| Данные обучения | DIV2K, LSDIR, SID — исследовательские наборы |
| Файлы | `yond-gru32n.fp32.onnx` — для процессора, `yond-gru32n.fp16.onnx` — для видеокарт и NPU, `yond-gru32n.json` — описание для Vaata |

Как получены файлы: `tools/ai/vaata_ai.py import-yond` загружает исходные веса, выгружает тайл сети в ONNX (fp32)
и делает его копию в fp16; входы и выходы остаются float32. Та же команда сверяет PyTorch и ONNX Runtime на
случайном тайле.

Изменения относительно оригинала: только формат — ONNX и копия в fp16. Веса не дообучались.
