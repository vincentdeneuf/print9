# print9

An upgraded, drop-in replacement for Python's `print` with:

- Line wrapping via `wrap` (per-object wrapping at a given width)
- ANSI coloring via `color` (predefined names or custom ANSI codes)
- Full compatibility — forwards standard `print()` kwargs like `sep`, `end`, `file`, `flush`

## Installation

```bash
pip install print9
```

## Quick start

```python
from print9 import print9

# Use both wrap and color
print9("Hello, world! This line will be wrapped and colored.", wrap=40, color="green")
```

## New Parameters

- **wrap: Optional[int]**
  - Max line width to wrap each object's text.
  - If `None` or `<= 0`, wrapping is disabled.
  - Example: `wrap=40` wraps long lines at 40 characters.
- **color: Optional[str]**
  - Color for each object's text.
  - Accepts predefined names or a custom ANSI escape code.
  - If `None`, no color is applied.

### Predefined color names

`black`, `red`, `green`, `yellow`, `blue`, `magenta`, `cyan`, `white`, `orange`, `purple`, `pink`, `brown`, `gray`.

## Examples

```python
from print9 import print9

# Wrap long text
long_text = """
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
""".strip()

print9(long_text, wrap=50)

# Use a predefined color
print9("Success!", color="green")

# Use a custom ANSI color (e.g., bright blue)
print9("Custom color", color="\x1b[94m")

# Combine multiple objects and forward kwargs to print()
print9("A", "B", "C", wrap=None, color=None, sep=" | ", end="\n\n")
```

## Notes

- Wrapping applies per object after converting it to a string.
- Coloring wraps each object's text with the chosen color and a reset code.
- All other keyword arguments are passed directly to Python's built-in `print()`.

## License

MIT License 2025 Vincent de Neuf. See [LICENSE](LICENSE) for details.

