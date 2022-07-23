# Engineering Practices

```For Data Scientists```

```By Juha Kiili (Valohai)```

## Git

Git is a version control system designed to track changes in a source code over time.

### Rules of thumb for Git

- Don't push datasets
- Don't push secrets
- Don't push notebook outputs (You can set up a pre-commit hook for git that clears outputs automatically)
- Don't use the --force (Unless you know what you're doing)
- Do small commits with clear descriptions
- Don't be afraid of branching & pull requests

## Python Dependencies

Dependency management is the act of managing all the external pieces that your project relies on.
Dependency management is documenting the required environment for your project and making it easy and deterministic for others to reproduce it.

The recommended way is to decouple the dependency information from the code in a standardized, reproducible, widely-accepted format.
This allows version pinning and easy deterministic installation.

> #Auto-generate requirements.txt
>
> pip-compile requirements.in

### Main takeaways

- Don't avoid dependency management
- Always use virtual environments on your local computer
- Pinning versions is better than not pinning
- Packages change a lot, Python not so much

## Docker

Docker isolates the software from all other things on the same system.

### The containerized stack

**Application**: High-level application (your data science project)

**Dependencies**: Low-level generic software (think Tensorflow or Python)

**Docker container**: The isolation layer

**Operating system**: Low-level interfaces and drivers to interact with the hardware

**Hardware**: CPU, Memory, Hard disk, Network, etc.

The fundamental idea is to package an application and its dependencies into a single reusable artifact, which can be instantiated reliably in different environments.

The flow to create Docker containers:

1. **Dockerfile**: Instructions for compiling an image
2. **Image**: Compiled artifact
3. **Container**: An executed instance of the image

### GPU Support

There are five prerequisites for a modern GPU (NVIDIA) container.

1. Image: CUDA/cuDNN libraries
2. Image: GPU versions of your framework like Tensorflow (when needed)
3. Host Machine: GPU Drivers
4. Host Machine: NVidia Docker Toolkit
5. Host Machine: Docker run executed with ```--gpus all```
