# How to Run the Jarvis Project

This guide provides step-by-step instructions to set up and run the Jarvis project, which includes an Android voice assistant app and a Python agent backend.

## Prerequisites

- **Python 3.8 or higher**: Download from https://www.python.org/.
- **Android Studio**: Download from https://developer.android.com/studio.
- **LiveKit CLI**: Install from https://docs.livekit.io/home/cli/cli-setup/.
- **LiveKit Cloud Account**: Sign up at https://cloud.livekit.io/.
- **Android Device or Emulator**: For running the Android app.

## Project Structure

- `MyJarvis/`: Android app source code.
- `agent.py`: Python agent script.
- `requirements.txt` / `req.txt`: Python dependencies.
- Other files: Configuration and documentation.

## Setup

### 1. Clone or Prepare the Project

Ensure the project is in `d:/Jarvis`. If not, clone or copy it there.

### 2. Set Up Python Virtual Environment

1. Open a terminal in `d:/Jarvis`.
2. Create a virtual environment:
   ```
   python -m venv venv
   ```
3. Activate the virtual environment:
   - On Windows: `.\venv\Scripts\activate`
   - On macOS/Linux: `source venv/bin/activate`
4. Install dependencies:
   ```
   pip install -r req.txt
   ```
   This installs LiveKit agents, plugins, and other required packages.

### 3. Set Up LiveKit Cloud Sandbox

1. Go to https://cloud.livekit.io/projects/p_/sandbox.
2. Create a new Sandbox Token Server.
3. Note the `sandbox_id` for later use.

## Running the Android App

1. **Install LiveKit CLI** (if not done):
   ```
   # Follow instructions at https://docs.livekit.io/home/cli/cli-setup/
   ```

2. **Clone and Connect the Template**:
   ```
   lk app create --template agent-starter-android --sandbox <your_sandbox_id>
   ```
   Replace `<your_sandbox_id>` with your actual sandbox ID.

3. **Open in Android Studio**:
   - Launch Android Studio.
   - Open the project: Navigate to `d:/Jarvis/MyJarvis` and select it.

4. **Build and Run**:
   - Click "Build" > "Make Project".
   - Connect an Android device or start an emulator.
   - Click "Run" > "Run 'app'".

The app will connect to your LiveKit sandbox and be ready for voice interactions.

## Running the Python Agent

1. Ensure the virtual environment is activated (from Setup step 2).
2. Run the agent:
   ```
   python agent.py dev
   ```
   This starts the Python agent in development mode, which handles voice processing and connects to LiveKit.

## Troubleshooting

- **Android Build Errors**: Ensure Android SDK is installed and updated in Android Studio.
- **Python Import Errors**: Verify all dependencies are installed with `pip list`.
- **LiveKit Connection Issues**: Check your sandbox ID and token server setup.
- **Emulator Not Starting**: Ensure virtualization is enabled in BIOS and HAXM is installed.
- **Agent Not Responding**: Confirm the agent is running and the Android app is connected to the same LiveKit room.

## Additional Resources

- LiveKit Documentation: https://docs.livekit.io/
- Android SDK Docs: https://developer.android.com/docs
- Python Virtual Environments: https://docs.python.org/3/tutorial/venv.html

For further assistance, check the existing README.md in `MyJarvis/` or contact the project maintainers.
