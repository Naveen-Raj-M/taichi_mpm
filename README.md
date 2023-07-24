# Granular Flow Simulation Using `taichi_mpm`
Simulating sand mass collision using [taichi mpm](https://github.com/taichi-dev/taichi_elements)

## Input
Using `input.json` file, granular mass can either be generated randomly in a specified domain,
or can be placed manually.

```shell
{
    "save_path": "./sand2d_collision/",
    "id_range": [
        0,
        10
    ],
    "domain_size": 1.0,
    "friction_angle": 35,
    "wall_friction": 0.43,
    "elastic_modulus": 2000000.0,
    "poisson_ratio": 0.3,
    "rho": 1800,
    "sim_space": [
        [
            0.1,
            0.9
        ],
        [
            0.1,
            0.9
        ]
    ],
    "sim_resolution": [
        64,
        64
    ],
    "nparticel_per_vol": 16384,
    "nsteps": 350,
    "mpm_dt": 0.0025,
    "gravity": -9.81,
    "gen_cube_randomly": {
        "generate": true,
        "ncubes": [1, 3],
        "min_distance_between_cubes": 0.01,
        "cube_size_range": [0.15, 0.40],
        "vel_range": [-2.5, 2.5],
        "cube_gen_space": [[0.11, 0.89], [0.11, 0.89]],
        "nparticle_limits": 20000
    },
    "gen_cube_from_data": {
        "generate": true,
        "sim_inputs": [
            {
                "id": 0,
                "mass": {
                    "cubes": [
                        [
                            0.1,
                            0.1,
                            0.1,
                            0.1
                        ]
                    ],
                    "velocity_for_cubes": [
                        [
                            1.0,
                            1.0
                        ]
                    ]
                },
                "obstacles": null
            }
        ]
    },
    "visualization": {
        "is_realtime_vis": false,
        "is_save_animation": true,
        "skip": 1
    }
}
```

## Output
The output is saved and `.npz` file. The code also saves simple `.gif` animation for the simulation. 

## Run
```shell
python3 mpm_collision.py
```

## Simulation Example
![Sand collision example](example.gif)



