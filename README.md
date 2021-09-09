# Data for the Ocean Surface plot

These data, collected from the [Global Drifters Program](http://www.aoml.noaa.gov/phod/gdp/index.php), where used in the following publication:

> **State aggregations in Markov chains and block models of networks**, <br>
> *Faccin, Schaub and Delvenne*,
> [Phys. Rev. Lett., 127(7) p.078301 (2021)](https://doi.org/10.1103/PhysRevLett.127.078301)<br>
> [ArXiv 2005.00337](https://arxiv.org/abs/2005.00337)

The data reported here aggregate all drifters trajectiories up to June 2017 and are not kept updated.

## Subdivision of the ocean

The subdivision of the ocean is in *square* cells, each corresponding to a node.
The Earth is divided into a grid of $100 \times 50$ cells with constant area.

## Nodes

Nodes or cells are reported in `data/net-nmap.json.gz`.
The file contains a dictionary of nodes as follows:

``` json5
{
    ...,
    "4999": [       // ID as string
        4999,       // ID as integer in [0: 5000)
        [
            49,     // x location in [0: 50)
            99      // y location in [0: 100)
        ],
        "ARCTIC OCEAN",  // a tag; do not trust it too much
        [
            78.52165904546642,   // latitude
            178.2                // longitude
        ]
    ],
    ...
}
```

## Links

Links between nodes are saved in:

```
data/net-t087.json.gz
```

It contains the drifter count that went from node 1 to node 2 in exactly 87 days.
The list in `coords` holds node ID pairs while the list in `data` keeps the count of drifters that went from node 1 to node 2.

``` json
{
    "coords": [
        ...,
        [23, 77],
        ...,
    ],
    "data": [
        ...,
        13,
        ...
    ]
}
```
