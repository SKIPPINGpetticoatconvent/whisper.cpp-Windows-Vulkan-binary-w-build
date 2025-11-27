# whisper.cpp Windows Vulkan Build

This repository contains a GitHub Actions workflow designed to build [whisper.cpp](https://github.com/ggerganov/whisper.cpp) with Vulkan acceleration enabled for Windows.

## Workflow Details

The workflow performs the following steps:
1.  Checks out the repository (including submodules).
2.  Installs the Vulkan SDK on the runner.
3.  Configures the project with CMake setting `-DGGML_VULKAN=ON`.
4.  Builds the release binaries.
5.  Bundles `glslc.exe`.
6.  Uploads the artifacts and optionally publishes a GitHub Release.

## How to Build

This workflow is configured to run **manually** (`workflow_dispatch`).

1.  Navigate to the **Actions** tab in this repository.
2.  Select the **Build Windows Vulkan** workflow from the left sidebar.
3.  Click the **Run workflow** button on the right side.
4.  (Optional) Enter a **Release Tag** (e.g., `v1.0.0`) if you want to create a GitHub Release. Leave empty to just build artifacts.
5.  Select the branch (usually `main` or `master`) and click the green **Run workflow** button.

## Artifacts and Releases

Once the build completes successfully, you can download the resulting binaries in two ways:

1.  **Artifacts**: From the workflow run summary page, download `whisper-windows-vulkan-binaries`.
2.  **Releases**: If you provided a Release Tag, a new release will be created in the **Releases** section of the repository containing a zip file (e.g., `whisper-windows-vulkan-v1.0.0.zip`).

The package contains:
*   `main.exe` (and other whisper.cpp examples)
*   `whisper.dll`
*   `glslc.exe`

## Requirements for Running

To run the executables downloaded from the artifacts:
*   A Windows machine.
*   A GPU with Vulkan support.
*   Appropriate graphics drivers installed.