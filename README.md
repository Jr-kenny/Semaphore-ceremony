# Semaphore-ceremony
## guide to participate in Semaphore trusted ceremony setup

<img width="680" height="358" alt="image" src="https://github.com/user-attachments/assets/3d09406d-18c6-4a94-a720-7bc5b6726298" />

Semaphore is a zero-knowledge protocol that allows people to prove things anonymously.
To make it work securely, the project runs a Trusted Setup Ceremony.

During the ceremony, thousands of people add random values into the system.
As long as one person is honest, the system becomes secure forever.

By contributing, you are helping make Semaphore stronger and censorship-resistant.

## Requirements Before You Start

1. GitHub account
Must be at least 1 month old.
At least 1 public repository.
Following at least 5 people.
Have at least 1 follower.
Allow access to Gists.

2. Operating system
Linux / MacOS / WSL (Windows Subsystem for Linux) / Ubuntu VPS.

3. Internet
Stable connection (≥ 10 Mb/s).
Stay online until your turn is done (sometimes hours).

## ✌️ Step 1 — Update System & Install Dependencies
On Ubuntu/Debian systems run:
```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt install curl screen build-essential git wget lz4 jq make gcc nano tmux htop unzip libssl-dev -y
```
## ✌️ Step 2 — Install Node.js (v18 with NVM)
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
source ~/.bashrc
nvm install 18
nvm use 18
```
## ✌️Step 3 — Create a Working Directory
```bash
mkdir ~/trusted-setup && cd ~/trusted-setup
```
## ✌️Step 4 — Install the Ceremony CLI
```bash
npm install -g @p0tion/phase2cli
```
## ✌️Step 5 — Authenticate with GitHub
```bash
phase2cli auth
```
.sign into github using the link on the terminal.
.input the code you're given on he terminal.
.return to the terminal after successfully signing in to proceed.

## ✌️Step 6 — Start the Contribution
It’s best to run inside a screen session (so it continues even if you disconnect).
we are opening a screen so the ceremony keeps going in the background—might take hours before it’s your turn.
Screen is useful for VPS, not WSL. If you close the terminal in WSL, your screen session is killed

1. Start screen session:
```bash
screen -S semaphore
```
2. Inside screen, run the contribution command:
```bash
phase2cli contribute -c semaphore-binary-merkle-root-fix
```
3. Wait your turn in the queue (may take hours).
When your contribution starts, it will generate random values and submit them.

## ✌️Step 7 — Managing screen
. Detach (leave it running): Ctrl + A, then press D
. Reattach:
```bash
screen -r semaphore
```
. List sessions:
```bash
screen -ls
```
. Kill session manually:
```bash
screen -XS semaphore quit
```

## ✌️Step 8 — Cleanup After You Finish
Once you’ve contributed successfully:
```bash
phase2cli clean
phase2cli logout
rm -rf ~/trusted-setup
```
## ⚡ Troubleshooting & FAQs
Timeout / connection lost?
Don’t panic — just restart the contribution:
```bash
phase2cli contribute -c semaphore-binary-merkle-root-fix
```
Why use screen?
If your internet drops, VPS disconnects, or you close your terminal, your contribution continues safely.

What if I don’t understand the cryptography?
That’s fine! Even without deep knowledge, your contribution adds real security to Semaphore.

## Final Note
You’ve now successfully joined the Semaphore Trusted Setup Ceremony.
Your small randomness contribution helps build a censorship-resistant, anonymous future.

## Optional:
Share your participation on X or other platforms

https://x.com/Jrken_ny
