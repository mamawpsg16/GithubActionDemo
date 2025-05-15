EXAMPLES 
1. * - Matches anything except slashes (/)
paths:
  - 'src/*.js'

Matches:
    src/app.js
    src/main.js

Does NOT match:
    src/utils/helper.js (because of the /)

2. ** - Matches any number of directories or files (recursive)
paths:
  - 'src/**'

Matches:
    src/app.js
    src/utils/helper.js
    src/components/button/index.js
    src/

Does NOT match:
    public/app.js

3. + - Matches one or more characters, excluding /
paths:
  - 'src/file+.js'
Matches:
    src/file1.js
    src/fileA.js
    src/fileXYZ.js

Does NOT match:
    src/file.js (because + requires at least one extra character)

4. ? - Matches exactly one character, excluding /
paths:
  - 'src/file?.js'
Matches:
    src/file1.js
    src/fileA.js

Does NOT match:
    src/file.js (too short)
    src/file12.js (too long)

5. ! -  Negation (excludes pattern)
paths:
  - 'src/**'
  - '!src/tests/**'

Matches:
    src/app.js
    src/components/button.js

Does NOT match:
    src/tests/test_app.js