# Code Coverage Report

## Summary

**Total Coverage: 33.57%** (480/1430 lines covered)

Generated with cargo-tarpaulin on: 2025-10-22

## Coverage by Module

### Main Library (tamc)

| Module | Coverage | Lines Covered | Total Lines |
|--------|----------|---------------|-------------|
| src/csr.rs | 81.25% | 39/48 | Good |
| src/ising.rs | 43.03% | 105/244 | Moderate |
| src/percolation.rs | 91.18% | 31/34 | Excellent |
| src/pt.rs | 58.21% | 195/335 | Moderate |
| src/ising_results.rs | 100.00% | 5/5 | Perfect |
| src/lib.rs | 5.71% | 2/35 | Low |
| src/util.rs | 1.01% | 1/99 | Low |
| src/gla.rs | 0.00% | 0/96 | None |
| src/sa.rs | 0.00% | 0/135 | None |
| src/main.rs | 0.00% | 0/10 | None |

### Binaries

| Binary | Coverage | Lines Covered | Total Lines |
|--------|----------|---------------|-------------|
| src/bin/percolate.rs | 0.00% | 0/24 | None |
| src/bin/tamc-pt-opt.rs | 0.00% | 0/130 | None |

### Core Library (tamc-core)

| Module | Coverage | Lines Covered | Total Lines |
|--------|----------|---------------|-------------|
| tamc-core/src/ensembles.rs | 100.00% | 7/7 | Perfect |
| tamc-core/src/sa.rs | 100.00% | 15/15 | Perfect |
| tamc-core/src/metropolis.rs | 88.00% | 22/25 | Excellent |
| tamc-core/src/pt.rs | 75.32% | 58/77 | Good |
| tamc-core/src/traits.rs | 0.00% | 0/3 | None |
| tamc-core/src/util.rs | 0.00% | 0/74 | None |
| tamc-core/src/parallel/ensembles.rs | 0.00% | 0/7 | None |
| tamc-core/src/parallel/pt.rs | 0.00% | 0/27 | None |

## Analysis

### Well-Tested Areas
- **Percolation**: 91.18% coverage - excellent test coverage for percolation algorithms
- **CSR (Compressed Sparse Row)**: 81.25% coverage - matrix representation well tested
- **tamc-core Ensembles**: 100% coverage - core ensemble sampling fully tested
- **tamc-core SA**: 100% coverage - simulated annealing implementation fully tested
- **tamc-core Metropolis**: 88% coverage - Metropolis sampling well tested

### Areas Needing More Tests
- **Utilities** (src/util.rs): Only 1% covered - need tests for file I/O and parsing
- **GLA** (src/gla.rs): 0% covered - graph-based local algorithm needs tests
- **SA wrapper** (src/sa.rs): 0% covered - simulated annealing wrapper needs tests
- **Parallel implementations**: 0% covered - parallel PT and ensemble code untested
- **Binaries**: 0% covered - command-line tools not covered by unit tests

### Recommendations

1. **Add utility tests**: Test file parsing, graph conversion, and data I/O functions
2. **Test parallel code**: Add tests for parallel implementations in tamc-core
3. **Integration tests for binaries**: Create integration tests for command-line tools
4. **Increase PT coverage**: Add more test cases for different PT configurations
5. **Test GLA module**: Add tests for graph local algorithm implementations

## Running Coverage Locally

Generate HTML coverage report:
```bash
cargo tarpaulin --out Html --output-dir coverage
```

View the report:
```bash
open coverage/tarpaulin-report.html  # macOS
xdg-open coverage/tarpaulin-report.html  # Linux
```

Generate XML for CI:
```bash
cargo tarpaulin --out Xml
```

## CI Integration

Coverage is automatically generated on every push and pull request via GitHub Actions.
See `.github/workflows/coverage.yml` for the workflow configuration.
