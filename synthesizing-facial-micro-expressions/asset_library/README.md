# Asset Library

A documented database of activation parameters and their corresponding simulated micro-expressions. One file per muscle or activation, named `<muscle>.md` (for example `zygomaticus_major.md`). Copy the template below.

```
# <Muscle / activation>

- Model / scene: <file and version>
- Activation parameters: <values, amplitude range, step>
- Material settings: <stiffness, damping, other solver settings>
- Reference footage: <source, clip id, frames>

## Simulated result
<What the simulated micro-expression looks like. Link figures or renders.>

## Comparison with reference
<Visual and numerical (strain / displacement) findings.>

## Usable range
<Activation values where the result is reliable.>

## Limitations
<Where and why it breaks down at micro-scales.>
```
