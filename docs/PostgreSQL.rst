
      `````{tabs}
         ````{group-tab} Bash, Linux or macOS

         Save the file as `pre-commit`
         ````
         ````{group-tab} Windows Anaconda prompt

         Save the file as `pre-commit.bat`
         ````
      `````

   The script is the same for all operating systems:
   ```shell
   #!/bin/bash

   pytest example.py
   ```
6. Make the script executable:
      `````{tabs}
         ````{group-tab} Bash, Linux or macOS

            ```console
            $ chmod +x pre-commit
            ```
         ````
         ````{group-tab} Windows Anaconda prompt

            Nothing to do.
         ````
      `````
7. Check the hook script:
      `````{tabs}
         ````{group-tab} Bash, Linux or macOS

            ```console
            $ ./pre-commit
            ```
         ````
         ````{group-tab} Windows Anaconda prompt

            ```console
            $ ./pre-commit.bat
            ```
         ````
      `````
8. Move this file under .git/hooks:
      `````{tabs}
         ````{group-tab} Bash, Linux or macOS

            ```console
            $ mv pre-commit .git/hooks
            ```
         ````
         ````{group-tab} Windows Anaconda prompt

            ```console
            $ move pre-commit.bat .git/hooks
            ```
         ````
      `````
9. Break the code (for example, change `+` to `-`) and try to commit this change.
   Now the `pre-commit` should reject the commit.
10. Discuss this approach: pros and cons.
````

```{solution}
Pros:
- Tests exist
- You won't forget to run it
- Doesn't depend on any other services

Cons:
- If tests take a long time, your computer is blocked
- Each person has to enable the commit hook separately (hooks are not part of Git history)
- Can't ensure the test was run
- Sometimes you want to commit a change which breaks a test but this way you cannot

```

```{keypoints}
- pytest collects and runs all test functions starting with `test_`.
- Python and C/C++ have better tooling for automated tests than Fortran and you can use those also for Fortran projects (via `iso_c_binding`).
- Git hooks provide a convenient way to *locally* automatize tests.
```
