Accelergy-Timeloop Processing-in-memory (PIM) Example
------------------------------
This repo contains a PIM example architecture and the associated constraints designed for the accelergy-timeloop
DNN accelerator evaluation framework.

### System Requirement
The following tools are needed to perform the simulations, 
- Option 1: install the accelegy-timeloop-infrastructure docker [here](https://github.com/nelliewu95/accelergy-timeloop-infrastructure)
- Option 2: manually install the following tools:
    - [accelergy](https://github.com/nelliewu95/accelergy)
    - [timeloop](https://github.com/NVlabs/timeloop)
    - [accelergy-table-based-plug-in](https://github.com/nelliewu95/accelergy-table-based-plug-ins)
    - [accelergy-cacti-plug-in](https://github.com/nelliewu95/accelergy-cacti-plug-in)
- Please add the provided PIM estimation tables using the command

  ```
  accelergyTables -r <path to this repo>/PIM_estimation_tables
  ```

### File Structure
- `arch` folder: the YAML files describing the architecture and the its associated components.
- `constraint` folder: describes a weight stationary dataflow with no weight reload.
- `PIM_estimation_tables` folder: contains necessary technology data for estimating the specific example architecture
- `mapper`: contains the mapspace exploration knobs
- `example_outputs`: contains the simulation outputs of the example workload running on the architecture

### Run example simulation
To run an example simulation:
```
timeloop-mapper arch/system_PIM.yaml arch/components/*.yaml mapper/mapper.yaml constraints/*.yaml example_layer.yaml
```
