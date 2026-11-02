# Среда выполнения

Сети запускаются в ONNX Runtime из Windows ML (Microsoft). DirectML даёт им любую видеокарту с DirectX 12, а Windows ML
сама подгружает драйверные провайдеры производителей — TensorRT для NVIDIA, OpenVINO для Intel, Vitis AI и QNN для
NPU, — если Windows их предлагает для этого компьютера.

Файлы среды здесь не хранятся: лицензия Microsoft разрешает распространять их только вместе с приложением, а не
отдельно. Когда среда впервые нужна, Vaata скачивает официальный пакет с nuget.org, проверяет его по SHA-256 и берёт
из него:

| Файл в пакете | Куда кладёт Vaata |
|---|---|
| `runtimes/win-x64/native/onnxruntime.dll` | `ai/runtime/onnxruntime.dll` |
| `runtimes/win-x64/native/DirectML.dll` | `ai/runtime/DirectML.dll` |
| `runtimes/win-x64/native/Microsoft.Windows.AI.MachineLearning.dll` | `ai/runtime/Microsoft.Windows.AI.MachineLearning.dll` |
| `license.txt` | `ai/runtime/license.txt` |
| `ThirdPartyNotices.txt` | `ai/runtime/ThirdPartyNotices.txt` |

Сам пакет после этого удаляется. Версия и хеш пакета вшиты в Vaata и перечислены в [`../catalog.json`](../catalog.json).
