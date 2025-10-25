# VR Test Smell Detection Tool

This tool is developed to automatically detect test smells in Unity-based Virtual Reality (VR) projects written in C#. It performs a static analysis of the project's test code to uncover poor testing practices, commonly referred to as "test smells." These smells may indicate maintainability issues, lack of clarity, or potential faults in the test suite. By identifying such issues early, the tool helps developers improve the overall quality and reliability of their test code, leading to more robust VR applications.

## UNZIP

please use VRTestSnifferTool.zip source code for VRTestSniffer Tool and to try VRTestSniffer with UI then use VRTestSniffer_tool_UI_.zip and follow the below instructions to run the tools.


## Features

- Detects 16 different types of test smells
- Analyzes both test code and production code metrics
- Generates comprehensive CSV reports
- Can process multiple projects in batch mode
- Provides both command-line and GUI interfaces
- Can be run directly from source without building JAR

## Supported Test Smells

- Assertion Roulette
- Eager Test
- Lazy Test
- Mystery Guest
- Sensitive Equality
- General Fixture
- Magic Number Test
- Default Test
- Redundant Print
- Constructor Initialization
- Sleepy Test
- Empty Test
- Ignored Test
- Exception Catching/Throwing Test
- Unknown Test
- Redundant Assert Test
- Duplicate Assert Test

## Installation

### Option 1: Using Pre-built JAR

1. Download the `VRTestSmellTool.jar` file
2. Ensure you have Java JDK 8 or later installed

### Option 2: Building from Source

1. Clone this repository
2. Ensure you have Java JDK 8 or later installed
3. Build the project using Maven:

```bash
mvn clean package
```

The built JAR file will be in the `target` directory

### Option 3: Running Directly from Source (No JAR needed)

1. Clone this repository
2. Import the project into your Java IDE
3. Set up the required dependencies (all included in the project)
4. Configure the root directory path in `MainClass.java`

## Usage

### Method 1: Running Without JAR File (Direct from Source)

1. Open `MainClass.java` in your IDE
2. Uncomment these lines:

```java
Scanner cin = new Scanner(System.in);
System.out.println("Enter an integer: ");
int inputidx = cin.nextInt();
```

3. Comment out this line:

```java
// int inputidx = Integer.parseInt(args[2]);
```

4. Run the `MainClass` directly from your IDE
5. When prompted, enter the number corresponding to the analysis you want to perform

#### First-Time Setup:

- You must run option `1` first to download all projects
- Or manually clone projects into the `GitRepo` folder under your root directory

#### Available Options:

```text
1 -> Download Projects
11 -> Generate Test and Functional code Method and Class Count (RQ1)
12 -> Generate Functional code LOC (RQ1)
2 -> Test Assert Density (RQ2 + LOC(RQ1) analysis)
31 -> Assert Roulette Analysis (RQ3)
32 -> Eager Test Analysis (RQ3)
33 -> Lazy Test Analysis (RQ3)
34 -> Mystery Guest Analysis (RQ3)
35 -> Sensitive Equality Analysis (RQ3)
36 -> General Fixture Analysis (RQ3)
37 -> Magic Number Test Analysis
38 -> Default Test Analysis
39 -> Redundant Print Analysis
40 -> Constructor Initialization
41 -> Sleepy Test
42 -> Empty Test
43 -> Ignored Test
44 -> Exception Catching/Throwing Test
45 -> Unknown Test
46 -> Redundant Assert Test
47 -> Duplicate Assert Test
48 -> No Smell Test Cases
49 -> Random Selection of Test Cases from a File
```

### Method 2: Using Pre-built JAR File

```bash
java -jar VRTestSmellTool.jar "<GitRepoURL>" "<OutputFolder>" <AnalysisOption>
```

Example:

```bash
java -jar VRTestSmellTool.jar "https://github.com/ExtendRealityLtd/Zinnia.Unity.git" "/home/user/output" 31
```

### Method 3: Graphical User Interface

1. Ensure you have Node.js and Electron installed
2. Navigate to the UI directory
3. Run:

```bash
npm install
npm start
```

In the UI:

- Enter the GitHub repository URL
- Specify the output folder
- Select the test smell to analyze from the dropdown
- Choose "No" for download option if you have already cloned the projects

## Configuration

Before running analyses:

- Set the root directory in `MainClass.java` by modifying the `selectedFolder` variable
- For first-time use, run option `1` to download all projects
- Alternatively, manually clone projects into the `GitRepo` folder under your root directory

## Output

Results are saved as CSV files in the root folder with the following pattern:

- `Final_[SmellName]_Smells_.csv` for smell analyses
- Other analyses follow similar naming conventions

Each CSV file contains:

- Project Name
- Test Function
- Smell Type (for smell analyses)
- Additional metrics depending on the analysis type

## Requirements

- Java JDK 11+
- Maven (for building)
- Git (for project downloading)
- Node.js (for GUI version)

## Troubleshooting

### If projects fail to download:

- Check your internet connection
- Verify the projects list in `Project_Source_.txt` contains valid URLs
- Manually clone projects into the `GitRepo` folder

### If analyses fail:

- Ensure all required projects are present in the `GitRepo` folder
- Verify the root directory path is correctly set
- Check for sufficient disk space and permissions

### For GUI issues:

- Ensure all Node.js dependencies are installed
- Verify the JAR file is named `VRTestSmellTool.jar` and is in the correct location

### For direct source execution:

- Ensure all dependencies are properly configured in your IDE
- Verify you've made the necessary code modifications to enable console input

## License

This project is licensed under the MIT License.