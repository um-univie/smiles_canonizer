# SMILES Canonizer

A fast and efficient command-line tool for canonicalizing SMILES (Simplified Molecular Input Line Entry System) strings. This tool supports both single SMILES string input and batch processing of files containing multiple SMILES strings.

## Features

- Canonicalize single SMILES strings or entire files
- Parallel processing support for faster batch operations
- Flexible output options (file or stdout)
- Automatic output file naming

## Usage

```bash
smiles_canonizer <input> <Options>
```
### Arguments

- `<input>`: Input file containing SMILES strings (one per line) or a single SMILES string

### Options

- `-o, --output <FILE>`: Output file path (defaults to input_filename_canonized.ext)
- `-s, --sequential`: Disable parallel processing
- `-p, --print`: Print results to stdout instead of writing to file
- `-h, --help`: Display help information
- `-V, --version`: Display version information

### Examples

Canonicalize a single SMILES string and print it
```bash
smiles_canonizer "CC(=O)O" -p
```
Process a file containing SMILES strings
```bash
smiles_canonizer input.smi
```
Process a file and specify output location
```bash
smiles_canonizer input.smi -o output.smi
```
Print results to terminal instead of file
```bash
smiles_canonizer input.smi --print
```
Process file without parallel processing
```bash
smiles_canonizer input.smi --sequential
```

## Output

The program will either:
- Write canonicalized SMILES to a file (default behavior)
- Print results to stdout (when using `-p` flag)

For file output, if no output path is specified:
- For file inputs: Creates `{input_filename}_canonized.{extension}`
- For SMILES string inputs: Creates `smiles_canonized.txt`

## Error Handling

Invalid SMILES strings are reported as errors in the output, while valid strings are canonicalized. The program continues processing even if some SMILES strings are invalid.
