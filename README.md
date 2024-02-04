SVGO mirror
===========

Mirror of SVGO for pre-commit.

For pre-commit: see https://github.com/pre-commit/pre-commit

For SVGO: see https://github.com/svg/svgo


### Using SVGO with pre-commit

Add this to your `.pre-commit-config.yaml`:

```yaml
-   repo: https://github.com/kytta/mirrors-svgo
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: svgo
```

If you're using pre-commit's `end-of-file-fixer`, it will conflict with SVGO
removing the newline to conserve size. There are two ways to fix this conflict:

1. Ignore SVG files for `end-of-file-fixer`:

   ```yaml
   - id: end-of-file-fixer
     exclude: '\.svg$'
   ```

2. Use SVGO's `--final-newline` argument:

   ```yaml
   - id: svgo
     args: [ --final-newline ]
   ```
