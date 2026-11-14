# Webots URDF Initializers — Python

Python starter templates and utilities for URDF robots in Webots. Built to eliminate setup friction so you can focus on simulation.

> **Note:** This repository is the dedicated Python successor to [`webots-urdf-initializers`](https://github.com/occiinnovations/webots-urdf-initializers), separated from compiled C/C++ controllers. This was in order to run the code as an external controller and integrate libraries.

## Repository Structure

```text
webots-python/        
├── src/          
│   ├── IRB4600/
│   ├── Puma560/
│   ├── UR5e/
│   └── UR10e/
├── utils/         
├── pyproject.toml
├── requirements.txt
└── README.md
```

## Quick Start

### 1. Install Dependencies

Make sure your terminal uses the same Python interpreter set in Webots (Tools > Preferences > General > Python command):

```bash
pip install -r requirements.txt
```

### 2. Run Directly From VS Code (`<extern>`)

Using VS Code lets you run and debug with F5, and makes it possible to use libraries alongside Webots.

1. Open your `.wbt` world in Webots.
2. In the **Scene Tree**, expand your robot node, select the **`controller`** field, and set it to **`<extern>`**.
3. Save the world (`Ctrl + S`) and press **Play** in Webots.
4. Add a `.vscode/launch.json` configuration pointing `WEBOTS_HOME`, `PYTHONPATH`, and `PATH` to your Webots installation (See the snippet below)

5. Open any starter template in `src/` inside VS Code and press **`F5`** to connect and run immediately. Make sure it is the same robot as the template.

## JSON Template

```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Run Webots Extern Controller",
            "type": "debugpy",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "env": {
                "WEBOTS_HOME": "C:\\Program Files\\Webots",
                "PYTHONPATH": "C:\\Program Files\\Webots\\lib\\controller\\python",
                "PATH": "${env:PATH};C:\\Program Files\\Webots\\lib\\controller;C:\\Program Files\\Webots\\msys64\\mingw64\\bin;C:\\Program Files\\Webots\\msys64\\mingw64\\bin\\cpp"
            }
        }
    ]
}
```

## License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.
