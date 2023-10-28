# Some useful commands with os module in Python
# List the contents of a directory
```bash
import os
os.listdir('.') 
```

# Rename file or the directory
```bash
os.rename('file_name1', 'file_name2')
```

# Change the permission settings on the file
```bash
os.chmod('my_script.py', 0o777)
```

# Create a directory / folder
```bash
os.mkdir('/folder_name')
```

# Remove any file
```bash
os.remove('file_name')
```

# Remove folders
```bash
os.rmdir('/folder_name')
```
