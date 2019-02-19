# Tuning Process

- First:

   - Tune Alpha

- Second:

   - Tune Beta
   - Tune Number of Hidden units
   - Tune Mini-Batch size

- Third:

   - Tune Learning Rate Decay
   - Tune Number of Hidden layers
   
Try random values when searching, don't use a grid to search for hyperparameter values
  
Coarse to Fine sampling Scheme: Zoom in to a hyperparameter space that performs well
  
# Scale to pick Hyperparameters
  
Sampling hyperparameters at random != Sampling hyperparameters at **uniformly** at random
  
We need to use a scale to randomly sample hyper parameters
  
Searching over a log scale to more uniformly search over a range of values
  
Take the log of the low value and high value, and that will be your range to search for
 
If we sample on a linear scale, if Beta is close to 1, then a small change in Beta will cause the results to be different

`0.999` and `0.9995` will have a huge difference

# Pandas vs Caviar

Panda: Train one model at a time

Caviar: Train multiple models in parallel



