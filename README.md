# 🚜 Haystack

Haystack is a powerful tmux-based process management tool designed for
streamlining development environments. It allows you to easily manage multiple
processes defined in a Procfile, providing a clean and efficient interface for
monitoring and controlling your development stack.

Haystack was designed to be a relatively drop-in replacement for the `bin/dev`
that ships with [Ruby on Rails][rails].

[rails]: https://rubyonrails.org/

![Haystack Screenshot](./doc/haystack-screenshot.png)

## Features

- **Procfile Support**: Easily start and manage multiple processes defined in a
  Procfile.
- **Tmux Integration**: Utilizes tmux for efficient terminal multiplexing and
  process management.
- **Colorized Output**: Each process output is uniquely colored for easy
  differentiation.
- **Combined Log View**: View all process logs in a single, combined window.
- **Environment Variable Support**: Automatically loads environment variables
  from `.env` files.
- **Easy Navigation**: Use Alt+[number] to quickly switch between process
  windows.
- **One-Command Shutdown**: Gracefully stop all processes with a single key
  combination (Ctrl+Q).
- **Self-Update Mechanism**: Easily update Haystack to the latest version with a
  simple command.

## Requirements

💁‍♂️ **TL;DR**: You need bash, tmux, curl, sed, and sort installed on your system.

- For macOS: `brew install tmux curl coreutils`
- For Ubuntu/Debian: `sudo apt-get install tmux curl`

---

To use Haystack effectively, you need to have the following installed on your
system:

1. **Bash**: Haystack is a Bash script and requires a Bash shell to run. Most
   Unix-like systems (Linux, macOS) have Bash installed by default.

2. **tmux**: Haystack relies heavily on tmux for process management and
  interface creation. Make sure you have tmux installed and accessible from your
  command line.
   - On macOS: You can install tmux using Homebrew with `brew install tmux`
   - On Ubuntu/Debian: Install using `sudo apt-get install tmux`
   - On other systems: Check your package manager or the [tmux GitHub
   page](https://github.com/tmux/tmux) for installation instructions.

3. **curl**: Used for downloading updates. It comes pre-installed on most
  systems, but if you don't have it:
   - On macOS: It should be pre-installed. If not, you can install it with
   Homebrew: `brew install curl`
   - On Ubuntu/Debian: Install using `sudo apt-get install curl`

4. **sed**: Used for text processing. It's typically pre-installed on Unix-like systems.

5. **sort**: Used for version comparison. The GNU version of sort with `-V`
  option is preferred. It's typically pre-installed on Linux  systems.
   - On macOS: The default `sort` might not support `-V`. You can install GNU
   coreutils (which includes `gsort`) with Homebrew: `brew install coreutils`

### Compatibility

Haystack is designed to work on Unix-like operating systems, including:

- Linux distributions (Ubuntu, Debian, CentOS, etc.)
- macOS
- WSL (Windows Subsystem for Linux)

Windows users should use WSL or a Unix-like environment to run Haystack.

## Installation

1. Download the Haystack script:

   ```sh
   curl -o bin/haystack https://raw.githubusercontent.com/philtr/haystack/main/haystack
   ```

1. Make the script executable:

   ```sh
   chmod +x bin/haystack
   ```

## Usage

1. Navigate to your project directory containing a Procfile.

1. Run Haystack:

   ```sh
   bin/haystack
   ```

   By default, Haystack looks for a file named `Procfile.dev`. If you want to
   use a different Procfile, specify it as an argument:

   ```sh
   bin/haystack Procfile.local
   ```

1. Haystack will start all processes defined in your Procfile within a tmux session.

1. Use the following commands within the Haystack session:
   - `Alt+[number]`: Switch to a specific process window
   - `Alt+1`: View the combined log output
   - `Ctrl+Q`: Gracefully shut down all processes and exit Haystack

## Updating Haystack

Haystack can be updated using the following commands:

- `bin/haystack --update`: Checks for updates and installs a new version if
  available.
- `bin/haystack --update --force`: Forces an update to the latest version, even
  if it's not newer than the current version.

## Configuration

Haystack uses the following files for configuration:

- `Procfile.dev` (or the specified Procfile): Defines the processes to run.
- `.env.development` or `.env`: Defines environment variables for your processes.

## Contributing

Contributions to Haystack are welcome! Please feel free to submit pull requests,
create issues, or suggest new features.

## License

Haystack is open-source software licensed under the MIT license.

## Author

Haystack is created and maintained by [@philtr](https://github.com/philtr). For questions,
suggestions, or support, please [open an
issue](https://github.com/philtr/haystack/issues) on the GitHub repository.

## AI Disclaimer

**PLEASE NOTE**: This project was almost entirely generated using AI. While efforts have
been made to ensure functionality and safety, users should use this software at their own
risk. Always review and test thoroughly before using in any critical environments. 
