# codex-loop

Review. Fix. Repeat. Powered by Codex.

A small CLI that runs a Codex review/fix loop on uncommitted changes until no actionable findings remain.

## Requirements

- Python 3.9+
- `codex` installed and available in `PATH`

## Usage

```bash
python codex_loop.py
python codex_loop.py --max-iters 5
python codex_loop.py --model gpt-5.1-codex-max
python codex_loop.py --show-extracted
```

## What it does

- Runs `codex exec review --uncommitted`
- Extracts actionable findings like `- [P1]`, `- [P2]`
- Asks Codex to apply minimal fixes
- Repeats until the review is clean or the max iteration limit is reached

## Notes

- Streams review output in real time
- Captures stdout and stderr for extraction
- Only reacts to actionable findings matching `- [P#]`
- Does not commit, push, rebase, or rewrite git history

## License

Apache-2.0
