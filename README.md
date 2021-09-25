# Safety Transfer Learning via Maximum Entropy Exploration 

To use the code for safe transfer learning, you need to install the updated [Safety Gym](https://github.com/qisong-yang/safety-gym). 

## Installation

To install this package:

```
git clone https://github.com/qisong-yang/safety-starter-agents.git

cd safety-starter-agents

pip install -e .
```

## Train a safe explorer

To get the safe explorer in a safety-constrained environment without reward signals, run :
```
cd /path/to/transfer

python saclag-maxent.py --logger_kwargs_str '{"output_dir": "./SafeExplorer"}'
```

### Transfer to a new task

The similarity between the teacher policy and the student policy is taken as a bonus `r'` during learning. Then, we get a new reward `r = r + αr'`

If `α` is fixed, run: 
```
cd path/to/transfer

python saclag-trans-fix.py  /path/to/SafeExplorer --logger_kwargs_str '{"output_dir": "./xxx"}'
```

If `α` decreases following a decay rate, run: 
```
cd path/to/transfer

python saclag-trans-dr.py  /path/to/SafeExplorer --logger_kwargs_str '{"output_dir": "./xxx"}'
```

If `α` is adaptive based on the safety performance, run: 
```
cd path/to/transfer

python saclag-trans-ada.py  /path/to/SafeExplorer --logger_kwargs_str '{"output_dir": "./xxx"}'
```
