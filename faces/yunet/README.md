# YuNet — поиск лиц

Крошечный детектор лиц (около 76 тысяч параметров): Wei Wu, Hanyang Peng, Shiqi Yu, «YuNet: A Tiny
Millisecond-level Face Detector», Machine Intelligence Research, 2023. Для каждого лица возвращает рамку,
уверенность и пять точек: глаза, кончик носа, углы рта. Vaata с его помощью находит все лица на фото в режиме «Лицо».

| | |
|---|---|
| Источник | OpenCV Zoo, <https://github.com/opencv/opencv_zoo/tree/main/models/face_detection_yunet> |
| Лицензия | MIT — файл [`LICENSE`](LICENSE) (Copyright (c) 2020 Shiqi Yu) |
| Файл | `face_detection_yunet_2026may.onnx` — вход любого размера, кратного 32; `yunet.json` — описание |

Как получен файл: `tools/ai/vaata_ai.py import-yunet` берёт его из OpenCV Zoo без изменений и проверяет, что он
запускается и выходы те же.
