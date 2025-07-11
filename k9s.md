K9s is a terminal-based UI to manage Kubernetes clusters. It simplifies the process of interacting with Kubernetes resources by providing an intuitive interface and commands to explore, monitor, and manage your cluster directly from the terminal.

# K9s Cheatsheet

## Installation

### Using Homebrew on macOS or Linux

1. Open a terminal.
2. Run the following command:

   ```bash
   brew install k9s
   ```

3. To verify the installation, type:

   ```bash
   k9s version
   ```

---

## Getting Started

- Launch the K9s UI:

  ```bash
  k9s
  ```

## Essential Commands

### Navigation

- Use arrow keys or `j`/`k` to navigate through resources.
- Press `/` to search within the current view.
- Press `?` to open the help menu.

### Resource Management

- Press `:` to enter command mode, then type a Kubernetes resource, e.g., `pods`, `deployments`.
- To describe a resource, highlight it and press `d`.
- To edit a resource, highlight it and press `e`.

### Logs

- View logs for a pod:
  - Highlight the pod and press `l`.
  - Filter logs by typing `/` after entering the logs view.

### Exiting

- Press `Ctrl+C` to quit k9s.

---
