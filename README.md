# Embedded DevOps Coding Challenge Template

## Overview

This repository serves as a template for the Embedded DevOps Coding Challenge. It provides a structured environment for candidates to demonstrate their skills in embedded systems development, continuous integration, and software compliance.

## Project Structure

The project is organized as follows:

```
.
├── .github/
│   └── workflows/
│       └── ci.yml                  # GitHub Actions CI configuration
├── .devcontainer/                   # Optional: Configuration for GitHub Codespaces
├── project/
│   ├── src/                        # Sample firmware code (currently empty)
│   └── Makefile                    # Build configuration
├── docs/
│   └── example-output.md           # Documentation for example outputs
├── metadata/
│   ├── sbom.spdx.json              # Sample Software Bill of Materials (SBOM)
│   ├── metadata.json               # Sample build information
│   └── firmware.sha256             # Sample SHA-256 hash for integrity verification
├── test_log.json (optional)        # Optional test logs
├── walkthrough.mp4 (placeholder)   # Placeholder for project walkthrough video
├── README.md                       # Project documentation
├── COMPLIANCE.md (optional)        # Optional compliance information
└── LICENSE                         # Licensing terms
```

## Challenge Instructions

1. **Clone the Repository**: Start by cloning this repository to your local machine.
   
   ```bash
   git clone https://github.com/your-username/embedded-devops-coding-challenge-template.git
   ```

2. **Set Up Your Environment**: If using GitHub Codespaces, the `.devcontainer` directory contains configuration files to set up a consistent development environment. Otherwise, ensure you have the necessary tools installed locally.

3. **Build the Project**: Navigate to the `project` directory and use the provided `Makefile` to build the firmware code.

   ```bash
   cd project
   make
   ```

4. **Run Tests**: Execute any tests you have implemented and log the results in `test_log.json`.

5. **Export SBOM**: After building, ensure to export the Software Bill of Materials (SBOM) in SPDX format.

6. **Document Your Work**: Update `docs/example-output.md` with logs, screenshots, or any relevant outputs from your work.

7. **Create a Walkthrough**: Record a video walkthrough of your solution and replace the placeholder `walkthrough.mp4` with your video.

8. **Submit Your Solution**: Once completed, submit your repository link as per the challenge guidelines.

## Compliance

Refer to `COMPLIANCE.md` for any compliance-related information and guidelines.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.