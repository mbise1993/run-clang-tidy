# run-clang
This is my modified version of the run-clang-tidy.py script. It:
* Automatically removes duplicate entries in the the `-export-fixes` file
* Supports a new `-pretty-print` option that, when used in conjunction with `-export-fixes`, writes the fixes out to a Markdown file
as well as the normal YAML file. It groups suggested fixes by file and provides a list of suggested fixes for each file, removing
duplicates. The generated Markdown looks something like this:

### ..\..\src\relative/path/ServiceProvider.h
* missing 'typename' prior to dependent type name 'std::enable_if<std::is_base_of<Service, T>::value>::type'

### C:\Users\Path\To\Project\src\libqt\controls/RbLabel.h
* function 'riffbox::RbLabel::RbLabel' has a definition with different parameter names

### C:\Users\Path\To\Project\src\score\models\Note.cpp
* statement should be inside braces

### C:\Users\Path\To\Project\src\libqt\Application.cpp
* statement should be inside braces
* inclusion of deprecated C++ header 'stdlib.h'; consider using 'cstdlib' instead
