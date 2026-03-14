- AMD-specific fork of Stable Diffusion WebUI
	- https://github.com/lshqqytiger/stable-diffusion-webui-amdgpu
- rocm6.2
	- possibly require override:
		- `HSA_OVERRIDE_GFX_VERSION=10.3.0 python main.py`
		  `# or for RDNA3 cards like the 7600:`
		  `HSA_OVERRIDE_GFX_VERSION=11.0.0 python main.py`
-