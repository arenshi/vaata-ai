# Лицензии

У каждой модели своя лицензия; её полный текст лежит в папке модели и в её релизе.

## YOND gru32n

MIT. Источник: <https://huggingface.co/spaces/hansen97/YOND>. Полный текст — в [`denoise/yond-gru32n`](denoise/yond-gru32n).

## YuNet

MIT. Источник: <https://github.com/opencv/opencv_zoo/tree/main/models/face_detection_yunet>. Полный текст — в [`faces/yunet`](faces/yunet).

## EasyPortrait SegFormer-B0 512

переработка CC BY-SA 4.0 от SberDevices, коммерческое использование разрешено. Источник: <https://github.com/hukenovs/easyportrait>. Полный текст — в [`faces/easyportrait-segformer-b0-512`](faces/easyportrait-segformer-b0-512).


## Среда выполнения

ONNX Runtime, DirectML и Windows ML — программы Microsoft из пакета NuGet
[`microsoft.windows.ai.machinelearning` 2.4.89](https://www.nuget.org/packages/microsoft.windows.ai.machinelearning/2.4.89). Здесь их нет: Vaata скачивает
пакет с nuget.org и берёт из него три библиотеки вместе с `license.txt` и `ThirdPartyNotices.txt`, которые кладёт рядом
с ними. Условия — [лицензия пакета](https://www.nuget.org/packages/microsoft.windows.ai.machinelearning/2.4.89/License).
