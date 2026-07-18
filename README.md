# get-module-underlying
Explore Python modules deeper than `dir()`.

## Installation

```bash
pip install get_module_underlying
```

## Usage

```python
from get_module_underlying import ModuleExplorer

# Explore a module
explorer = ModuleExplorer('sys')

# Get all attributes (excluding __xxx__)
print(explorer.get_all_attrs())

# Get only public attributes
print(explorer.get_public_attrs())

# Get private attributes (single underscore)
print(explorer.get_private_attrs())

# Get dunder attributes (__xxx__)
print(explorer.get_dunder_attrs())

# Get callable methods/functions
print(explorer.get_callable_attrs())

# Get non-callable attributes (variables, constants)
print(explorer.get_non_callable_attrs())

# Get attributes with their values
print(explorer.get_attrs_with_values())

# Get attributes with their types
print(explorer.get_attrs_with_types())

# Get all classes
print(explorer.get_classes())

# Get all functions
print(explorer.get_functions())

# Get all builtins
print(explorer.get_builtins())

# Get all submodules
print(explorer.get_modules())

# Get detailed module info
print(explorer.get_module_info())

# Get statistics summary
print(explorer.get_stats())

# Get Python system info
print(explorer.get_sys_info())

# Get module file info
print(explorer.get_file_info())

# Get everything at once
print(explorer.get_everything())
```

## Methods Reference

| Method | Return Type | Description |
|--------|-------------|-------------|
| `get_all_attrs()` | `{'valid': bool, 'data': list}` | All attributes except dunder (`__xxx__`) |
| `get_public_attrs()` | `{'valid': bool, 'data': list}` | Attributes not starting with `_` |
| `get_private_attrs()` | `{'valid': bool, 'data': list}` | Attributes with single `_` prefix |
| `get_dunder_attrs()` | `{'valid': bool, 'data': list}` | Dunder attributes (`__xxx__`) |
| `get_callable_attrs()` | `{'valid': bool, 'data': list}` | Callable functions/methods |
| `get_non_callable_attrs()` | `{'valid': bool, 'data': list}` | Non-callable variables/constants |
| `get_attrs_with_values()` | `{'valid': bool, 'data': dict}` | Attribute names with their values |
| `get_attrs_with_types()` | `{'valid': bool, 'data': dict}` | Attribute names with their types |
| `get_classes()` | `{'valid': bool, 'data': list}` | All classes in the module |
| `get_functions()` | `{'valid': bool, 'data': list}` | All functions in the module |
| `get_builtins()` | `{'valid': bool, 'data': list}` | All built-in functions |
| `get_modules()` | `{'valid': bool, 'data': list}` | All submodules imported |
| `get_module_info()` | `{'valid': bool, 'data': dict}` | Module metadata (name, file, doc, etc.) |
| `get_stats()` | `{'valid': bool, 'data': dict}` | Statistical summary of all attributes |
| `get_sys_info()` | `{'valid': bool, 'data': dict}` | Python system information |
| `get_file_info()` | `{'valid': bool, 'data': dict}` | Module source file information |
| `get_everything()` | `{'valid': bool, 'data': dict}` | All information combined |

## Return Format

All methods return a dictionary with the following structure:

```python
{
    'valid': True,          # bool: True if module is valid, False otherwise
    'data': ...             # The actual data (list or dict)
}
```

If the module is not valid, the method will:
- Emit a `ValidNotTrueWarning` warning
- Return `{'valid': False}`

## Dependencies

- Python 3.6+
- `absent` library (automatically installed)

## License

MIT
