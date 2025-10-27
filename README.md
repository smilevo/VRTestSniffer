# VRTestSniffer 🛠️

## Test Smell Detector for Virtual Reality (VR) Software Projects

**VRTestSniffer** is a static analysis tool specifically designed to detect **test smells** (anti-patterns in test code) within Virtual Reality (VR) software projects, particularly those developed using the **Unity** engine.

By automatically identifying common weaknesses and maintainability issues in VR test suites, VRTestSniffer helps developers improve the quality, reliability, and long-term maintainability of their VR testing efforts.

-----

## 🌟 Features

  * **VR-Specific Smells:** Focuses on a catalog of test smells that are uniquely challenging or prevalent in VR/Unity testing environments.
  * **Static Analysis:** Analyzes source code without requiring test execution, making it fast and efficient.
  * **Unity Compatibility:** Built to seamlessly process and analyze Unity-based projects.
  * **Quality Improvement:** Pinpoints areas for refactoring, leading to more robust, understandable, and less flaky test suites.

-----

## ⚙️ Installation

As a static analysis tool, the installation typically involves building the project from source.

### Prerequisites

  * **.NET SDK** (Required for building and running C\# projects)
  * **Git** for cloning the repository.
  * A **Unity Project** containing the test code you wish to analyze.

### Steps

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/smilevo/VRTestSniffer.git
    cd VRTestSniffer
    ```
2.  **Build the Project:**
    *(The specific build command may vary, but typically uses the .NET CLI for C\# projects)*
    ```bash
    dotnet build VRTestSniffer.sln 
    ```

-----

## 🚀 Usage

Once built, you can run VRTestSniffer from your command line, pointing it to the directory of your Unity project's test files.

### General Command Structure

```bash
# Run the tool, specifying the path to your Unity project's test directory
./VRTestSniffer --project-path /path/to/your/Unity/Project/Assets/Tests 

# Example: Run analysis and output results to a JSON file
./VRTestSniffer -p C:\Users\user\MyVRGame\Assets\Tests -o vr_smell_report.json
```

### Key Command-Line Arguments (Hypothetical)

| Argument | Description | Default |
| :--- | :--- | :--- |
| `-p`, `--project-path` | **Required.** Path to the root or test directory of the Unity project. | |
| `-o`, `--output` | File path for the generated smell report (e.g., JSON, XML). | `report.json` |
| `-v`, `--verbose` | Enable verbose output for detailed analysis logs. | `false` |

-----

## 🤝 Contributing

We welcome contributions\! If you have suggestions for new smell detectors, bug reports, or feature enhancements, please follow these steps:

1.  Fork the repository.
2.  Create your feature branch (`git checkout -b feature/NewSmellDetector`).
3.  Commit your changes (`git commit -m 'feat: Added detection for FlakyVRTest smell'`).
4.  Push to the branch (`git push origin feature/NewSmellDetector`).
5.  Open a Pull Request detailing your changes.

-----

## 📜 Citation

If you use VRTestSniffer in an academic context or research, please cite the associated research paper:

```
@inproceedings{Gurramkonda2025VRTestSniffer,
  title={{VRTestSniffer}: Test Smell Detector for Virtual Reality (VR) Software Projects},
  author={Gurramkonda, Faraz and others},
  booktitle={Proceedings of the 40th IEEE/ACM International Conference on Automated Software Engineering (ASE)},
  year={2025}
}
```

-----

## 👨‍💻 Authors

  * **Faraz Gurramkonda** - *Initial Author* - [GitHub: faraz07-AI](https://www.google.com/search?q=https://github.com/faraz07-AI)

-----

## 📄 License

This project is licensed under the **MIT License** - see the `LICENSE` file for details.
