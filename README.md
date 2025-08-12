# ComfyUI TorchInductorConfig

Welcome! This set of custom nodes for ComfyUI is all about unlocking the power of `torch.compile` and the Inductor backend. These nodes are designed to give you more control and insight into PyTorch's Inductor, helping you optimize your workflows and squeeze out more drops of performance! ⚡

## 🛠️ Installation

Follow these simple steps to get the node up and running in your ComfyUI environment.

### Step 1. Clone the Repository

First, you need to clone this repository into your `ComfyUI/custom_nodes/` directory.

Open your terminal or command prompt and navigate to your ComfyUI installation folder.

**For a standard PC installation:**
```bash
cd ComfyUI/custom_nodes/
git clone https://github.com/PixWizardry/Comfyui_TorchInductorConfig
```

### Step 2: Restart ComfyUI

After the repository has been successfully cloned, make sure to restart ComfyUI. This will allow it to recognize and load the new custom node. The nodes should be available in the "WAN" and "WAN/diagnostics" categories!

---

## ✨ Available Nodes

Here is a list of the nodes included in this package.

### TorchInductorOptimizer
This is the main node for applying powerful optimization strategies globally before `torch.compile` does its magic. It simplifies the complex task of configuring the Inductor backend.

*   **Optimization Strategy**: Choose from a list of pre-configured strategies, from stable heuristics to maximum autotuning.
*   **Reset to Defaults**: A handy toggle to clear all Inductor and Dynamo settings before applying a new strategy. This is great for debugging or ensuring a clean slate.
*   **Fine-Tuning Options**: Enable more specific optimizations like pointwise autotuning or specify backends for matrix multiplication (GEMM).

### InductorConfigPrinter
Ever wondered what configurations the Inductor's heuristics are generating for your specific hardware? This node tells you exactly that.

*   **Function**: It cleverly monkey-patches the Inductor backend to intercept and print the `triton.Config` objects being generated.
*   **Use Case**: An essential debugging tool to understand why a kernel might be performing a certain way and to see the direct output of the autotuning process.

### GPUInspector
A simple but very useful utility to get quick information about your GPU.

*   **Function**: Displays your GPU's device name, its compute capability (e.g., 8.6 for an RTX 3080), and the corresponding architecture code (e.g., `sm86`).
*   **Use Case**: Helps you quickly verify your hardware and understand its capabilities, which is crucial for performance tuning.
