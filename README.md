# fury

## Usage 

- The function below loads each unit in series.
- The unit name is the unit shellscript name without teh `.sh` extension

```shell
function fury_loader {
    units=(
        "pcd"
    )
    for i in "${units[@]}"; do
        eval "$(curl -sSL "https://raw.githubusercontent.com/matt-wiley/fury/main/units/${i}.sh")"
    done

    unset -f fury_loader
}
fury_loader
```