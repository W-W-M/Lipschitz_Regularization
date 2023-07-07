# Learning Smooth Neural Functions via Lipschitz Regularization

This is my re-implementation of the paper: Learning Smooth Neural Functions via Lipschitz Regularization Hsueh-Ti Derek Liu, Francis Williams, Alec Jacobson, Sanja Fidler, Or Litany SIGGRAPH (North America), 2022 [[Preprint](https://www.dgp.toronto.edu/~hsuehtil/pdf/lipmlp.pdf)]

### Dependencies
This re-implementation depends on PyTorch and common python dependencies (e.g., numpy, tqdm, matplotlib, etc.). 
Some functions in the script, such as generating analytical signed distance functions and the lipschitz linear layer, depend on functions in the folder `utils` and `models` respectively.

### Repository Structure
- `01__2D_interpolation` contains the script to train a Lipschitz MLP to interpolate 2D signed distance functions of a cross and a star. `main_mlp.py` and `main_lipmlp.py` is the main training script for a simple mlp and a lipschitz mlp, respectively. To train the model from scratch, simply run
```python
python main_lipmlp.py
```
After training (~15 min on a CPU), you should see the interpolation results in the sub-folder `mlp` and `lipmlp` and the model parameters in `mlp_params.pt` and `lipmlp_params.pt`.


- `model.py` contains the Lipschitz MLP model. One can simply use it as
```python
model = lipmlp(hyper_params) # build the model
params = model.initialize_weights() # initialize weights
y = model.forward(params, latent_code, x) # forward pass
```


### Results
![alt text](https://github.com/whitneychiu/lipmlp_pytorch/blob/main/interpolation_comparison.png?raw=true)

### Contact
This is my re-implementation of the paper. If there are any questions, please contact **Whitney Chiu** <wchiu@gatech.edu>
