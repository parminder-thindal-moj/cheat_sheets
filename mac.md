# Commands:

For Apple Silicon Devices (M1/M2), run the following command to get brew commands working in the terminal.

You need to add Homebrew to your PATH in ~/.zprofile:

`echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile`
`eval "$(/opt/homebrew/bin/brew shellenv)"`
