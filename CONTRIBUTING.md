# Contributing

Contributions to this project are released to the public under the repository license terms.

Everyone is welcome to contribute by opening issues, improving documentation, suggesting enhancements, or submitting pull requests.

## How to Contribute

### Reporting Issues

If you found a bug or have a feature idea:

1. Check if a similar issue already exists.
2. Open a new issue with:
   - Clear title and short summary
   - Steps to reproduce
   - Expected behavior vs actual behavior
   - Environment details (OS, Node.js version, browser)

### Submitting Pull Requests

1. Fork the repository.
2. Create a branch:
   ```bash
   git checkout -b feature/short-description
   ```
3. Run the app and verify changes locally.
4. Keep commits focused and clearly titled.
5. Open a pull request with:
   - Purpose of the change
   - Screenshots (for UI changes)
   - Manual test steps

## Code Style Guidelines

This project uses:

- JavaScript with React/Next.js
- CSS Modules for component/page styles
- Functional React components with hooks

Before submitting:

```bash
npm install
npm run dev
npm run build
```

## Coding Standards

1. Keep components focused and readable.
2. Use clear naming for props, state, and handlers.
3. Prefer small reusable UI components in `src/components`.
4. Keep route-level logic in `src/pages`.
5. Keep styles close to components using CSS Modules.
6. Avoid hardcoding configuration values in many places.
7. Document non-obvious logic with short comments.

## Adding or Updating Features

When adding functionality:

1. Update UI in relevant component(s) under `src/components`.
2. Update route/page behavior in `src/pages`.
3. Keep styles in matching `*.module.css` files.
4. Verify filtering/sorting/navigation behavior still works.
5. Update `README.md` and `INSTRUCTIONS.md` if flow or setup changed.

## UI/UX Guidelines

- Preserve responsive behavior for table/list and details pages.
- Keep sorting and filtering intuitive and fast.
- Ensure keyboard-accessible controls where possible.
- Keep visual hierarchy consistent with current design.

## Questions or Need Help?

- Or Assayag <orassayag@gmail.com>
- GitHub: <https://github.com/orassayag>
- StackOverflow: <https://stackoverflow.com/users/4442606/or-assayag?tab=profile>
- LinkedIn: <https://linkedin.com/in/orassayag>

Thank you for contributing.
