# Customer Slip Generator

[![Sponsor SagarBiswas-MultiHAT on Polar.sh](https://img.shields.io/badge/Sponsor-Polar.sh-0062FF?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://buy.polar.sh/polar_cl_I7DT5UQNUs1Qjb4VrFYOiRA2nkb3RVVUJCnjr3o5SGK)<br>
![Build](https://github.com/SagarBiswas-MultiHAT/CustomerSlip-CLI/actions/workflows/cmake.yml/badge.svg) 
![C++](https://img.shields.io/badge/c%2B%2B-C%2B%2B17-blue) 
![Tests](https://github.com/SagarBiswas-MultiHAT/CustomerSlip-CLI/actions/workflows/cmake.yml/badge.svg) ![License](https://img.shields.io/badge/license-MIT-green) 
![Last commit](https://img.shields.io/github/last-commit/SagarBiswas-MultiHAT/CustomerSlip-CLI)

Customer Slip Generator is a small, production-quality C++17 CLI that captures customer details, calculates totals, prints a clean slip, and persists records to CSV and JSONL with atomic writes for safe, durable storage.

## Requirements

- CMake 3.16+
- C++17 compiler (GCC 9+, Clang 10+, or MSVC 2019+)

## Build

### Linux/macOS

```bash
cmake -S . -B build -D CMAKE_BUILD_TYPE=Release
cmake --build build
```

### Windows (MSVC + Ninja)

```powershell
cmake -S . -B build -G Ninja -D CMAKE_BUILD_TYPE=Release
cmake --build build
```

## Run

### Interactive mode

```bash
./build/customer_slip
```

### View slips by name (case-insensitive)

```bash
./build/customer_slip --view "ada"
```

### Export CSV to pretty JSON

```bash
./build/customer_slip --export-json
```

## Sample outputs

### Sample interactive session

```
$ ./build/customer_slip

===== Enter Customer Details =====
Name: Sagar Biswas
Phone: +8801727371077
Address: XYZ Motijheel, Dhaka - 1000
Price: 120.50
Discount (%): 10

===== Product Slip =====
Name:     Sagar Biswas
Phone:    +8801727371077
Address:  XYZ Motijheel, Dhaka - 1000
Price:    $120.50
Discount: 10.00%
Total:    $108.45

Slip saved to data/slips.csv and data/slips.jsonl.
```

### Exact CSV line produced

```
name,phone,address,price,discount,total,timestamp
Ada Lovelace,+1-555-0100,"42 Analytical Engine Way, London",120.50,10.00,108.45,2026-02-01T12:34:56Z
```

### Exact JSONL line produced

```
{"name":"Ada Lovelace","phone":"+1-555-0100","address":"42 Analytical Engine Way, London","price":120.50,"discount":10.00,"total":108.45,"timestamp":"2026-02-01T12:34:56Z"}
```

## Tests

```bash
cmake -S . -B build -D CMAKE_BUILD_TYPE=Release
cmake --build build
ctest --test-dir build --output-on-failure
```

A green test run indicates core formatting and parsing logic is correct.

## Support MultiHAT Open-Source

If you find this project useful in your workflow, development, or security research, consider supporting **SagarBiswas-MultiHAT** in its ongoing maintenance and future updates (supports both One-Time and Monthly backing):

[![Support on Polar.sh](https://img.shields.io/badge/Support%20on-Polar.sh-0062FF?style=for-the-badge&logo=githubsponsors&logoColor=white)](https://buy.polar.sh/polar_cl_I7DT5UQNUs1Qjb4VrFYOiRA2nkb3RVVUJCnjr3o5SGK)
[![Portfolio](https://img.shields.io/badge/Portfolio-sagarbiswas.multihat.dev-2563EB?style=for-the-badge&logo=todoist&logoColor=white)](https://sagarbiswas.multihat.dev/)
[![Agency](https://img.shields.io/badge/Agency-multihat.dev-111827?style=for-the-badge&logo=vercel&logoColor=white)](https://multihat.dev)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for coding style, branching, and PR checklist.

## Changelog & roadmap

See [CHANGELOG.md](CHANGELOG.md) for release notes and planned enhancements.
