# running make_test_image not working out of the box

>>> Running: /home/thompson/software/microtorch/.venv/bin/python3 -m microtorch.utils.make_test_image -m VERDICT -g simulation_data/grad/grad_verdict.txt
<frozen runpy>:128: RuntimeWarning: 'microtorch.utils.make_test_image' found in sys.modules after import of package 'microtorch.utils', but prior to execution of 'microtorch.utils.make_test_image'; this may result in unpredictable behaviour
No YAML configuration found for VERDICT model.
Falling back to parsing model name for compartments: ['V', 'E', 'R', 'D', 'I', 'C', 'T'].
Parameter ranges will be the default compartment values.
Traceback (most recent call last):

Error is: 
File "/home/thompson/software/microtorch/.venv/lib/python3.13/site-packages/microtorch/model_maker.py", line 217, in model_compartments
    cls = getattr(signal_models_module, class_name)
AttributeError: module 'microtorch.signal_models' has no attribute 'V'

This works:
./scripts/create_all_test_images.py --model 'Stick' --grad simulation_data/grad/grad_verdict.txt

and we can find out model classes we can make with
grep class src/microtorch/signal_models/*.py

The integration test mentioned in the manuscript is absent.
