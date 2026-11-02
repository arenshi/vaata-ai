# EasyPortrait SegFormer-B0 512 — разбор лица на части

Сеть сегментации из набора EasyPortrait (SberDevices): Karina Kvanchiani, Elizaveta Petrova, Karen Efremyan,
Alexander Sautin, Alexander Kapitanov, «EasyPortrait — Face Parsing and Portrait Segmentation Dataset»,
arXiv:2304.13509. Делит вырезанное лицо на фон, кожу, левую и правую бровь, левый и правый глаз, губы и зубы.
EasyPortrait — единственный открытый набор с отдельной разметкой зубов. Vaata по этим маскам ретуширует кожу,
белки глаз и зубы в режиме «Лицо».

| | |
|---|---|
| Авторы и веса | <https://github.com/hukenovs/easyportrait>, чекпойнт `segformer-fp-512.pth` |
| ONNX | выгрузка sadzip: <https://huggingface.co/sadzip/EasyPortrait-ONNX>, файл `segformer_b0_fp_512.onnx` |
| Лицензия | «Public license with attribution and conditions reserved» от SberDevices — переработка CC BY-SA 4.0, файл [`LICENSE.pdf`](LICENSE.pdf); <https://github.com/hukenovs/easyportrait/blob/main/license/en_us.pdf> |
| Файлы | `segformer_b0_fp_512.onnx`, `easyportrait.json` — описание: вход, нормировка, классы |

Лицензия разрешает воспроизводить и распространять материал, в том числе в изменённом виде и в коммерческих целях,
при условии указания авторов, лицензии и изменений; изменённый материал распространяется на тех же условиях.
Материал предоставляется «как есть», без гарантий (раздел 5 лицензии).

Как получен файл: `tools/ai/vaata_ai.py import-easyportrait` скачивает выгрузку sadzip и исходный чекпойнт
авторов и сверяет веса: каждый тензор чекпойнта найден в ONNX-файле, а свёртки декодера с их нормализацией —
в свёрнутом виде, как их складывает выгрузка.

Изменения относительно оригинала: веса не менялись; формат ONNX — выгрузка sadzip. Vaata файл не изменяет.
