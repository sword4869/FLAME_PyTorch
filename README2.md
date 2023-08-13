```
model
├── FLAME2017
│   ├── Readme.pdf
│   ├── Readme.pdf:Zone.Identifier
│   ├── female_model.pkl
│   ├── female_model.pkl:Zone.Identifier
│   ├── generic_model.pkl
│   ├── generic_model.pkl:Zone.Identifier
│   ├── male_model.pkl
│   └── male_model.pkl:Zone.Identifier
├── FLAME2023
│   ├── FLAME Readme.pdf
│   ├── flame2023.pkl
│   └── flame2023_no_jaw.pkl
├── flame_model
│   ├── FLAME_sample.ply
│   ├── flame_dynamic_embedding.npy
│   └── flame_static_embedding.pkl
```

```
python main.py --flame_model_path model/FLAME2023/flame2023.pkl --static_landmark_embedding_path model/flame_model/flame_static_embedding.pkl --dynamic_landmark_embedding_path model/flame_model/flame_dynamic_embedding.npy
```


```
libGL error: MESA-LOADER: failed to open swrast: /usr/lib/dri/swrast_dri.so: cannot open shared object file: No such file or directory (search paths /usr/lib/x86_64-linux-gnu/dri:\$${ORIGIN}/dri:/usr/lib/dri, suffix _dri)
libGL error: failed to load driver: swrast
Traceback (most recent call last):
  File "/home/lab/project/FLAME_PyTorch/main.py", line 89, in <module>
    pyrender.Viewer(scene, use_raymond_lighting=True)
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyrender/viewer.py", line 347, in __init__
    self._init_and_start_app()
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyrender/viewer.py", line 995, in _init_and_start_app
    super(Viewer, self).__init__(config=conf, resizable=True,
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyglet/window/xlib/__init__.py", line 133, in __init__
    super(XlibWindow, self).__init__(*args, **kwargs)
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyglet/window/__init__.py", line 538, in __init__
    context = config.create_context(gl.current_context)
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyglet/gl/xlib.py", line 105, in create_context
    return XlibContext(self, share)
  File "/home/lab/miniconda3/envs/ldm/lib/python3.10/site-packages/pyglet/gl/xlib.py", line 127, in __init__
    raise gl.ContextException('Could not create GL context')
pyglet.gl.ContextException: Could not create GL context
```
```bash
sudo mkdir -p  /usr/lib/dri
conda install -c conda-forge gcc
sudo ln -s /usr/lib/x86_64-linux-gnu/dri/swrast_dri.so /usr/lib/dri/swrast_dri.so
```