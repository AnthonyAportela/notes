The main goal of this hackathon project is to integrate a couple of neural network models within CMSSW. The workflow for implementing any model onto L1 is as follows:

- Design an architecture in python
- Implement compression (quantization and pruning)
- Train the model
- Convert into firmware (aka cpp and hls)

After this there's a fork in the road. You have to go down both these paths in order for CMS to allow you to have you algorithm on L1.

1. Deploying the firmware onto hardware
2. Emulating the model in CMSSW

**(2) is the main focus of this hackathon.**

The workflow from here is to make two main components:
- The loader (aka emulator)
- The produces

The loader is this piece of code which translates in CMSSW inputs into something the models can understand, then converts the output of the model back into something CMSSW can understand.

> CMSSW inputs -->> model inputs -->> model -->> model outputs -->> CMSSW outputs


