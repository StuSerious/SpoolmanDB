# SpoolmanDB

A centralized place to store information about 3D printing filaments and their manufacturers.

The database is hosted using GitHub Pages, you can browse it at: [https://donkie.github.io/SpoolmanDB/](https://donkie.github.io/SpoolmanDB/)

You can contribute to this database by adding/editing files and submitting pull requests in this repository.

## Filaments

The source files are in the `filaments` folder. When this database is deployed, they will be expanded/compiled into a single JSON file called `filaments.json`.

To limit the amount of duplication needed in the source files, each combination of weight, color and diameter will be represented in the compiled JSON. For example, if you specify two diameters, two weights, and two colors, you will get eight combinations in the JSON. There isn't currently any way to exclude specific combinations; either you will have to live with the database having invalid
entries or you can split up the filament object into multiple ones.

### Filament file fields

| Field                   | Description                                                                                                                                               |
| ----------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `name`                  | The product name. Should probably contain the format code `{color_name}` to automatically insert the color name.                                          |
| `material`              | The material name, e.g., PLA.                                                                                                                             |
| `density`               | The density of the material in g/cm³.                                                                                                                     |
| `weights`               | An array of objects with `weight`, `spool_weight`, and `spool_type` fields. Specify multiple if the manufacturer sells the filament in different weights. |
| `diameters`             | An array of diameters in mm. Specify multiple if the manufacturer sells the filament in different diameters.                                              |
| `extruder_temp`         | *(optional)* Manufacturer recommended extruder temperature in °C.                                                                                         |
| `bed_temp`              | *(optional)* Manufacturer recommended bed temperature in °C.                                                                                              |
| `finish`                | *(optional)* The finish of the filament, e.g., "matte" or "glossy". Only set this if the filament is designed with this in mind.                          |
| `multi_color_direction` | *(optional)* The direction of the multi-color filament, e.g., "coaxial" or "longitudinal".                                                                |
| `pattern`               | *(optional)* Textured pattern, either "marble" or "sparkle" is currently supported. Feel free to add additional ones in the schema if necessary.          |
| `translucent`           | *(optional)* Boolean true/false if this filament is at least partially see-through.                                                                       |
| `glow`                  | *(optional)* Boolean true/false if this filament has a glow-in-the-dark effect.                                                                           |
| `colors`                | An array of objects with `name` and `hex` fields. Name should be what the manufacturer calls it. Hex should be the hex code of the color.                 |

## Materials

All materials are found in the `materials.json` file.

### Material file fields

* `material` - The material name, e.g. PLA.
* `density` - The density of the material in g/cm3.
* `extruder_temp` - General extruder temperature for this material.
* `bed_temp` - General bed temperature for this material.
