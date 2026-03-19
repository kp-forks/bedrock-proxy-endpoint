---
name: npm-audit
description: Run npm install and npm audit to fix vulnerabilities in both root and example directories
disable-model-invocation: true
---

# npm-audit

Run `npm install` and `npm audit` to fix vulnerabilities in both root (`./`) and client (`./example`) directories.

## Instructions

When this skill is invoked:

1. Navigate to the root directory (`./`) and run:
   - `npm install` to ensure all dependencies are up to date
   - `npm audit fix` to automatically fix vulnerabilities
   - If there are vulnerabilities that cannot be auto-fixed, run `npm audit` to show the report

2. Navigate to the client directory (`./example`) and run:
   - `npm install` to ensure all dependencies are up to date
   - `npm audit fix` to automatically fix vulnerabilities
   - If there are vulnerabilities that cannot be auto-fixed, run `npm audit` to show the report

3. Provide a summary of:
   - How many vulnerabilities were found in each location
   - How many were fixed automatically
   - Any remaining vulnerabilities that need manual attention

4. If vulnerabilities remain that require breaking changes, try using package.json `overrides`:
   - Check if the vulnerability is in a sub-dependency (a dependency of a dependency)
   - Add or update the `overrides` section in package.json with the minimum safe version
   - Example: For `flatted <=3.4.1` vulnerability, add `"flatted": ">=3.4.2"` to overrides
   - Run `npm install` in the affected directory to apply the override
   - Verify with `npm audit` that vulnerabilities are resolved
   - This approach avoids breaking changes to direct dependencies while patching vulnerable sub-dependencies

5. If code changes are needed to fix vulnerabilities:
   - **ALWAYS ask the user for permission first** before making any code changes
   - Clearly explain what needs to be updated and why (e.g., "Package X needs to upgrade from v2 to v3, which requires updating the import syntax in file.js")
   - After getting approval, make the necessary code updates
   - **Report all changes made** - list each file modified and what was changed
   - Re-run `npm audit` to verify the fixes worked
   - Provide a final summary of all actions taken

## Notes

- Always run `npm install` before `npm audit` to ensure the lock file is up to date
- Use `npm audit fix` to automatically fix vulnerabilities where possible
- **Prefer using `overrides` in package.json** to fix sub-dependency vulnerabilities before resorting to `npm audit fix --force`
  - This avoids breaking changes to direct dependencies
  - Both root and client package.json files already have `overrides` sections
  - Add the vulnerable package with its minimum safe version (e.g., `"flatted": ">=3.4.2"`)
- For breaking changes that can't be fixed with overrides, you may need to use `npm audit fix --force` (but ask the user first)
- If major version upgrades are needed, check the package's changelog/migration guide before making code changes
- Report the results clearly so the user knows what action was taken
- Keep the user informed throughout the entire process
