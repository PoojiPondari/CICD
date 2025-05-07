**Coding Challenge – Embedded DevOps Engineer**

---

### 🌟 Objective

Build and document a CI/CD pipeline that compiles, tests, and verifies a sample embedded firmware project targeting Arm. The pipeline should simulate hardware validation (virtual or physical), embed SBOM and traceability metadata into the build, and align with modern software supply chain and compliance best practices.

---

### 🌎 Background (Context)

In regulated domains like automotive and industrial IoT, embedded software must be delivered with high levels of automation, compliance, and traceability. InfoMagnus, in partnership with GitHub, Arm, and ELISA, helps organizations modernize their firmware development by building DevOps pipelines with embedded compliance, testing virtualization, and secure artifact generation. This challenge mimics that environment.

---

### 📦 Challenge Scope

You are tasked with automating a sample embedded software delivery pipeline using GitHub Actions. The workflow should simulate the full lifecycle from build to test to artifact verification and documentation.

---

### 🔧 Project Requirements

#### **Build Stage**

* Use a simple embedded project (e.g., Blinky for STM32 or Zephyr RTOS Hello World).
* Use `arm-none-eabi-gcc` or `west` (for Zephyr) to cross-compile.
* Produce a `.elf` or `.hex` binary artifact.

#### **Test/Validation Stage**

* Simulate execution using **Renode** or **QEMU**. HIL steps may be included if you have access to physical hardware.
* Include at least one automated test (mock or output-based).
* (Optional Bonus) Capture UART or GPIO simulation output as test log.

#### **Traceability & Metadata**

* Embed Git metadata (e.g., SHA, build timestamp, version) either within the binary or export in a metadata file (e.g., `.json`).
* Use `git rev-parse` or `git describe` for version derivation.
* Generate an SPDX SBOM in JSON format aligned with SPDX 2.3 or later.
* Add a validation step that confirms SPDX output is well-formed (e.g., using a linter or schema validator).

#### **Security & Verification**

* Use SHA256 or similar algorithm to compute integrity hash of the final artifact.
* Upload the following to GitHub Actions artifacts or GitHub Releases:

  * Binary output (`.elf` or `.hex`)
  * Metadata file (`.json`)
  * SBOM (`.spdx.json`)
  * Integrity hash file (e.g., `firmware.sha256`)
  * Optional: test output log (e.g., UART or simulation trace)

#### **Documentation**

Provide a `README.md` explaining:

* How the project builds and runs (locally and via CI)
* How traceability and SBOM are generated and validated
* How test output is verified
* Sample CI logs or screenshots
* Comments in all YAML workflows and scripts

#### **Deliverables Table**

| Deliverable                | Description                                      |
| -------------------------- | ------------------------------------------------ |
| `.elf` or `.hex`           | Compiled firmware binary                         |
| `metadata.json`            | Git SHA, timestamp, version, toolchain used      |
| `sbom.spdx.json`           | SPDX-formatted SBOM (2.3 or later)               |
| `firmware.sha256`          | SHA256 checksum                                  |
| GitHub Actions YAML        | Pipeline workflows                               |
| `README.md`                | Build/test documentation                         |
| (Optional) `COMPLIANCE.md` | Optional scenario reflections                    |
| (Optional) `test_log.json` | Captured UART or simulation output               |
| `walkthrough.mp4`          | Mandatory project video walkthrough (max 5 mins) |

---

### 🎯 Optional Bonuses (Stretch Goals)

* Add rollback handling logic in case of a failed test step.
* Capture Renode/QEMU logs as structured output (JSON or plain text).
* Use GitHub Actions **matrix strategy** to simulate multiple targets (e.g., Cortex-M0, M3, M4).
* Add `.devcontainer/` config to support GitHub CodeSpaces.

---

### 📤 Submission

Please submit:

* A GitHub repository link (public or private is fine)
* A video walkthrough in **MP4 format** (max 5 minutes), demonstrating your solution and uploaded directly to the project repository. Use **Git LFS** if necessary to manage large file size.
* Expected completion time: **5–7 days** from receipt

---

### 🔍 Scenario Simulation (Optional Bonus)

In 200–300 words (in `COMPLIANCE.md` or inline in `README.md`), choose **one**:

* How would you extend this pipeline to integrate with Corellium or Siemens EDA?
* What changes would you make to meet ISO 26262 or FDA traceability requirements?

---

### ⚖️ Evaluation Criteria

| Area                               | Weight | Description                                      |
| ---------------------------------- | ------ | ------------------------------------------------ |
| CI/CD pipeline implementation      | 25%    | Completeness, clarity, reuse of GitHub Actions   |
| SBOM & metadata generation         | 20%    | SPDX compliance, accuracy, traceability          |
| Embedded realism                   | 15%    | Proper toolchain, testing simulation, or HIL use |
| Security & verification            | 10%    | Hashing, release handling, optional signing      |
| Documentation & coaching potential | 20%    | README quality, clarity, sample logs             |
| Bonus efforts                      | 10%    | Simulation output, rollback, matrix, CodeSpaces  |

---
