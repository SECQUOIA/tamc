# TAMC - Quick Start Guide

## ✅ Installation Complete!

Your TAMC library is now built and ready to use.

## 📁 Project Structure

- **Binary executable**: `./target/release/tamc`
- **Library crates**: `tamc` and `tamc-core`
- **Example files**: Created for testing

## 🚀 Usage

### Basic Command

```bash
./target/release/tamc <method-file.yaml> <instance-file.txt> <output-file.yaml>
```

### Example Run

```bash
# Using the provided example files
./target/release/tamc example_method.yaml example_instance.txt output_results.yaml
```

### Input Files

**1. Method File (YAML)** - Simulation parameters
- `example_method.yaml` contains recommended settings for Parallel Tempering
- Key parameters:
  - `num_sweeps`: Number of Monte Carlo sweeps
  - `beta`: Temperature schedule (inverse temperature)
  - `num_replica_chains`: Number of parallel chains
  - `icm`: Iterated Conditional Modes for optimization

**2. Instance File (TXT)** - Ising problem specification
- Format: `i j K` (space or tab separated)
- `i == j`: K is a bias term
- `i != j`: K is a coupling strength
- Example: `example_instance.txt` defines a 3-variable problem

**3. Output File (YAML)** - Results
- Ground state energy
- Convergence statistics
- Acceptance rates
- Ground state configurations

## 🔧 Additional Options

### Sample Output
```bash
./target/release/tamc --sample-output samples.dat method.yaml instance.txt output.yaml
```
- Saves thermal samples in binary format
- Use `.pkl` extension for Python pickle format

### QUBO Format
```bash
./target/release/tamc --qubo method.yaml instance.txt output.yaml
```

### Susceptibility Measurements
```bash
./target/release/tamc --suscepts coeffs1.txt coeffs2.txt method.yaml instance.txt output.yaml
```

## 📚 Using as a Library

Add to your Rust project's `Cargo.toml`:

```toml
[dependencies]
tamc = { path = "/home/bernalde/repos/tamc" }
tamc-core = { path = "/home/bernalde/repos/tamc/tamc-core" }
```

Then in your code:

```rust
use tamc::ising::BqmIsingInstance;
use tamc_core::traits::*;
```

## 🔨 Rebuilding

After making changes:

```bash
# Debug build (faster compilation)
cargo build

# Release build (optimized, slower compilation)
cargo build --release
```

## 🧪 Testing

Run the test suite:

```bash
cargo test
```

## 📖 Additional Binaries

The project includes additional utilities:

1. **percolate** - Percolation simulations
   ```bash
   ./target/release/percolate
   ```

2. **tamc-pt-opt** - Parameter optimization for Parallel Tempering
   ```bash
   ./target/release/tamc-pt-opt
   ```

## 🎯 Next Steps

1. ✅ Library built successfully
2. ✅ Example files created
3. ✅ Test run completed
4. Create your own Ising problem instances
5. Adjust method parameters for your specific problem
6. Explore thermal sampling and susceptibility measurements

## 📝 Notes

- The ground state energy from the example: **-1.9000013**
- Build completed with 117 warnings (mostly unused imports - safe to ignore)
- For large problems, use `--release` builds for better performance

Happy Monte Carlo sampling! 🎲
