# EduXPU
**A Modular Simulator & Compiler for Next-Gen Processing Units**

EduXPU is an open-source educational framework that bridges the gap between modern heterogeneous hardware and accessible learning environments. It provides a lightweight yet powerful **simulator and compiler system** that allows students, researchers, and developers to explore next-generation processing paradigms—from GPUs and TPUs to emerging accelerators like DPUs and custom domain-specific units—without requiring specialized or expensive hardware.

---

##  Overview

EduXPU democratizes accelerated computing education by providing a sandbox where users can **learn, test, and prototype parallel programming models, memory hierarchies, and instruction-level designs** that drive cutting-edge HPC and AI systems.

---

##  Motivation

- **Barrier to Entry:** Learning GPU/accelerator programming requires access to costly hardware.
- **Complexity:** Different accelerators (CUDA, OpenCL, OpenACC, SYCL) demand steep learning curves.
- **Future-Readiness:** Students and developers need a safe environment to explore "what-if" architectures and learn optimization principles.

EduXPU addresses these gaps by combining **simulation, compilation, and visualization** in a modular platform.

---

##  Core Objectives

### Simulator Layer
- Modular, configurable simulator mimicking next-gen processing units:
  - **Execution units:** GPU-style SIMT cores, TPU-like systolic arrays, custom accelerators.
  - **Memory hierarchies:** Registers, caches, shared memory, global DRAM, HBM emulation.
  - **Instruction pipelines and scheduling policies.**

### Compiler Layer
- Lightweight frontend and IR (intermediate representation) to:
  - Translate high-level parallel constructs into simulated instructions.
  - Support OpenACC-like directives, CUDA-style kernels, and SYCL-inspired abstractions.
  - Allow extensibility for new ISAs or accelerator types.

### Educational Focus
- Visual debugging, performance metrics, and bottleneck visualization:
  - Warp/thread divergence visualization.
  - Memory access pattern analysis.
  - Instruction pipeline traces.
  - Energy/performance trade-offs (estimates).

### Prototype & Learn
- Enable "what-if" experimentation for students:
  - Change cache sizes, warp widths, instruction latency.
  - Experiment with different parallel programming models.
  - Observe effects in real-time.

---

##  Target Users

- **Students & Educators:** For classroom teaching of GPU/accelerator concepts without needing physical GPUs.
- **Researchers:** For early-stage architecture exploration.
- **Developers:** To understand optimization bottlenecks before deploying on real hardware.

---

##  Architecture

```
+-------------------+      +-------------------+      +-------------------+
|   Source Kernel   | ---> |   Compiler Front  | ---> |   Intermediate    |
| (Toy CUDA/ACC/SYCL)|     | (Parser & IR Gen) |      | Representation    |
+-------------------+      +-------------------+      +-------------------+
                                                           |
                                                           v
+-------------------+      +-------------------+      +-------------------+
|   Simulator Core  | ---> |   Memory Model    | ---> |   Visualization   |
| (SIMT, Systolic)  |     | (Registers, Cache)|      | (CLI/Plots)       |
+-------------------+      +-------------------+      +-------------------+
```

- **Frontend:** CLI (MVP), optional web dashboard for visualization.
- **Compiler:** Python-based parser for toy parallel language, IR generator.
- **Simulator:** Python modules for execution units, memory, and scheduling.
- **Visualization:** Matplotlib/Plotly for execution traces and performance metrics.

---

##  Features (Prototype)

- [x] Parse simple parallel kernels (vector add, matrix multiply) with CUDA/OpenACC-like syntax.
- [x] Generate and display intermediate representation (IR).
- [x] Simulate execution on a GPU-like SIMT core.
- [x] Model basic memory hierarchy (registers, shared, global).
- [x] Output execution traces and memory access patterns.
- [x] Allow users to tweak architecture parameters (warp size, cache size, etc.).
- [x] Provide demo kernels and quickstart instructions.

---

##  Getting Started

### Prerequisites

- Python 3.9+
- pip

### Installation

```bash
git clone https://github.com/your-org/EduXPU.git
cd EduXPU
pip install -r requirements.txt
```

### Quickstart

```bash
# Run a sample kernel through the compiler and simulator
python run.py --kernel examples/vector_add.xpu --visualize
```

- See `examples/` for sample kernels.
- Output includes IR, execution trace, and simple visualizations.

---

## Visualization Examples

- **Thread Divergence:**  
  ![Thread Divergence Example](docs/images/thread_divergence.png)
- **Memory Access Patterns:**  
  ![Memory Access Example](docs/images/memory_access.png)
- **Pipeline Trace:**  
  ![Pipeline Trace Example](docs/images/pipeline_trace.png)

---

## Roadmap

We are already in the design and early development phase. Here’s our focused plan for the hackathon prototype:

- [ ] **Day 1–2:**  
  - Backend API scaffolding (FastAPI or Flask)  
  - Container orchestration prototype (Docker/Kubernetes)  
  - Basic PostgreSQL schema for users and jobs  
  - Initial authentication and user management

- [ ] **Day 3–4:**  
  - Frontend dashboard setup (React + Tailwind)  
  - Student/lab views and job submission UI  
  - Integrate backend API with frontend  
  - Implement basic activity logging

- [ ] **Day 5:**  
  - GPU job submission and monitoring  
  - Secure sandboxing for user workloads  
  - JupyterLab integration for interactive labs  
  - Smart scheduling (fair-share/priority policies)

- [ ] **Day 6:**  
  - End-to-end demo with sample ML/system lab  
  - Polish README and documentation  
  - Prepare demo script and slides  
  - Collect feedback and finalize MVP

- [ ] **(Optional/Stretch):**  
  - Add usage analytics and reporting  
  - Enable multi-user collaboration in labs  
  - Deploy on cloud test cluster for live demo

---

##  Team Roles

- **Systems/Simulator:** Execution units, memory, scheduling
- **Compiler/Frontend:** Parser, IR, CLI
- **Visualization:** Metrics, plots, dashboards
- **Docs/Education:** Demos, assignments, documentation

---

##  License

This project is licensed under the MIT License.

---

##  Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

##  References

- [CUDA Programming Guide](https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html)
- [OpenACC Specification](https://www.openacc.org/specification)
- [SYCL Specification](https://www.khronos.org/sycl/)
- [Educational GPU Simulators](https://github.com/accel-sim/accel-sim-framework)

---

**EduXPU – Prototype, Learn, and Accelerate!**

This is just the beginning thought we have right now