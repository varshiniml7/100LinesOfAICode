# ⚡ Terminal AI

**Natural language shell** - Describe what you want, get safe shell commands.

## Quick Start

```bash
pip install anthropic
export ANTHROPIC_API_KEY=your_key

python terminal.py
python terminal.py find all large files
```

## Example Session

```
💭 What do you want to do? find all Python files modified today

💻 Command: find . -name "*.py" -mtime -1
📖 Explanation: Searches for Python files modified in last 24 hours
⚠️  Risks: None

❓ Execute? [y/N]: y

📤 Output:
./agent.py
./terminal.py
```

## Safety Features

- **Safe Mode**: Blocks `rm -rf /`, fork bombs, disk wiping
- **Risk Warnings**: Shows potential dangers before execution
- **Explanations**: Understand what each command does

## Troubleshooting

- **Missing API key (`ANTHROPIC_API_KEY not found`)**
  Set the environment variable first: `export ANTHROPIC_API_KEY="your-key"`
  Get your key at https://console.anthropic.com/

- **anthropic package not installed**
  Install it with: `pip install anthropic`

- **API or network errors**
  Terminal AI automatically retries Anthropic calls 3 times with a short backoff.
  If errors persist, check your internet connection or try again later.

- **Command timed out**
  Shell commands are limited to 30 seconds to keep the experience responsive.
  Try a narrower request or run the suggested command manually in your terminal.

## Common Uses

```bash
python terminal.py find all .log files older than 30 days
python terminal.py show memory usage
python terminal.py list top 10 CPU-consuming processes
python terminal.py compress all images in this folder
```

**88 lines. Safe by default.**
