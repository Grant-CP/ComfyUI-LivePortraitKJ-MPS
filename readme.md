# MPS Notes from Grant

If you wish to incorporate these changes into your repo, feel free to open an issue and ask. The commits should be pretty clear, and I also label almost all changes with #HACK so a full text search will work too. 

Please let me know if you decide to incorporate any of these changes into your LivePortrait implementation so I can direct people to you repository. I do not intend to maintain this repo.

Some operations are simply not supported on MPS and I didn't rewrite them. Most of my changes are just to `.cuda` calls and that sort of thing. Many operations are still done on CPU, so don't expect awesome performance.

On my M1 macbook 32GB it takes around 30 seconds flat + 1 second per video frame. 32 frames is 57 seconds, 600 frames is 650 seconds. VRAM usage is not dependent on video length. I never started using swap, but make sure to open up activity monitor and check if you are on a lower-end model. I'm pretty sure it only took 9 GB VRAM but I didn't profile it carefully.

# ComfyUI nodes to use [LivePortrait](https://github.com/KwaiVGI/LivePortrait)


https://github.com/kijai/ComfyUI-LivePortrait/assets/40791699/e55e10f6-af61-4d73-b162-af29eb847516


I have converted all the pickle files to safetensors: https://huggingface.co/Kijai/LivePortrait_safetensors/tree/main

They go here (and are automatically downloaded if the folder is not present) `ComfyUI/models/liveportrait`


Insightface is also required.
If you have a working compile encironment, installing it can be as easy as:

`pip install insightface`

or for the portable version, in the ComfyUI_windows_portable -folder:

`python_embeded/python.exe -m pip install insightface`

If this fails (and it's likely), you can check the Troubleshooting part of the reactor node for alternative:

https://github.com/Gourieff/comfyui-reactor-node

For insightface model, extract this to `ComfyUI/models/insightface/buffalo_l`:

https://github.com/deepinsight/insightface/releases/download/v0.7/buffalo_l.zip

*Please note that insightface license is non-commercial in nature.*
