# Problem solve
- [[Time Series Forecasting]]

# Implemented with
- [[RNN]]

#  Data type support
- [[JSON Line Format]]
![[Pasted image 20210624213357.png]]

# How is it should be used
- Include entire time series for training, testing and validation
- Use entire dataset as testing => Remove last time series for training
- Dont use very large values for prediction length (>400)
- Train on many time series and not just one

# Data reading mode
- [[File reading mode]] ~ read all in once
- [[Pipe reading mode]] ~ read in batch

# Instance support type
- [[Multi GPU]]
- [[Multi CPU]]
- [[Multi Machine]]