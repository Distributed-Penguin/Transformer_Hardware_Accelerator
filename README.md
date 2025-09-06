About

This project implements a hardware accelerator for the self-attention mechanism at the core of Transformer models, designed to improve efficiency on resource-constrained edge devices.

Transformers have revolutionized deep learning across domains such as natural language processing, computer vision, and time-series prediction, but their self-attention operation is computationally and energy intensive. To address this, we developed and verified a hardware-friendly solution that balances accuracy, performance, and resource usage.

Key Features

Fixed-Point Arithmetic (Q5.10):
Replaces floating-point operations with a compact 16-bit fixed-point format, reducing hardware complexity while maintaining numerical stability.

Custom Multiply–Accumulate (MAC) Unit:
Enables efficient matrix multiplications for Query, Key, and Value projections.

Softmax Approximation:
Implemented using lookup tables (LUTs), piecewise linear interpolation, and deterministic truncation, allowing real-time exponential evaluation without costly floating-point hardware.

Python-to-Verilog Workflow:
A Python reference model validates correctness before migration to Verilog. Inputs are quantized into Q5.10 format and compared across both implementations to ensure functional accuracy.

Verification & Performance:
Side-by-side testing demonstrates correctness of the Verilog design, with substantial runtime improvements over the Python baseline, highlighting the potential of dedicated accelerators for low-latency and low-power inference.

Outcomes

The results show that dedicated hardware can significantly accelerate Transformer inference, making real-time deployment feasible for applications such as mobile AI, embedded systems, and IoT devices. This work paves the way for scalable and energy-efficient deployment of advanced AI models on the edge.
