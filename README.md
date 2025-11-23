# sherpa-onnx-static-libs-x64


Static libraries for Sherpa-ONNX (Piper) and ONNX Runtime. Fully compiled for MSVC/C++ (x64 /MD), eliminating external DLLs for native applications and game mods.


# 🚀 Sherpa-ONNX Static Libraries (MSVC x64 /MD)

This repository provides **statically compiled** libraries for Sherpa-ONNX (Piper TTS) and ONNX Runtime. These libraries are built for MSVC 2022 (x64 /MD), designed to eliminate external DLL dependencies for high-performance C++ applications and game mods.


--

## 💾 Integration Guide (Visual Studio / C++ Projects)

### 1. Include Directories

Ensure your compiler can find the headers:

* **C/C++ -> General -> Additional Include Directories:**
    * Add the path to your cloned `include/` folder (e.g., `$(SolutionDir)Dependencies\include`).

### 2. Linker Dependencies (CRITICAL INPUT)

You must link the entire suite of static libraries. Add the following list to your **Linker -> Input -> Additional Dependencies** settings:

| Component | Files to Link (.lib) |
| :--- | :--- |
| **Sherpa-ONNX Core** | `sherpa-onnx-c-api.lib`, `sherpa-onnx-core.lib` |
| **Sherpa Internal** | `kaldi-native-fbank-core.lib`, `ssentencepiece_core.lib`, `kaldifst_core.lib` |
| **ONNX Runtime (Essential)** | `onnxruntime_session.lib`, `onnxruntime_providers.lib`, `onnxruntime_framework.lib`, `onnxruntime_graph.lib`, `onnxruntime_common.lib`, `onnxruntime_flatbuffers.lib`, `onnxruntime_mlas.lib`, `onnxruntime_util.lib` |
| **System Libs** | `Shlwapi.lib`, `dxgi.lib` |

---
