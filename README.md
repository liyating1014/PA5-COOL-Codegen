# PA5 COOL Codegen (report snippets)

This repo packages the code snippets shown in the PA5 report into a clean GitHub-ready layout.

## Structure
- `pa5_patch/`: snippets to merge into your PA5 `cgen.cc/cgen.h`
- `tests/`: sample `.cl` inputs
- `scripts/`: helper scripts for generating and diffing outputs

## Typical workflow (inside your PA5 directory)
```bash
make clean
make

# generate my asm
./lexer tests/good.cl | ./parser tests/good.cl 2>&1 | ./mycgen tests/good.cl 2>&1 > my_good.s

# generate official asm
./lexer tests/good.cl | ./parser tests/good.cl 2>&1 | /usr/class/bin/cgen tests/good.cl 2>&1 > official_good.s

diff my_good.s official_good.s
```

## Scripts
Copy this repo’s `scripts/` into your PA5 directory (or run from there):
```bash
bash scripts/gen_and_diff_good.sh
```
