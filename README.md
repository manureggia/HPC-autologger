# HPC-autologger
a basic script for auto logging on ssh tunnel for Unimore's HPC Course

## Use

To start ssh tunnel 

```bash
hpc-tunnel start <OPTIONAL:PORT>
```
> if not specified it will connect to a pre-configured `PORT`

To close ssh tunnel

```bash
hpc-tunnel stop
```
To login into your Jetson nano use

```bash
hpc-tunnel login
```
