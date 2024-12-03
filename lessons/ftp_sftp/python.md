### Example FTP Session Using Python

You can use the `ftplib` module in Python to perform FTP operations.

1. **Install ftplib**:
   - `ftplib` is included in the Python Standard Library, so no installation is needed.

2. **Python Script for FTP Operations**:

   ```python
   from ftplib import FTP

   # Connect to the FTP server
   ftp = FTP('ftp.example.com')
   ftp.login(user='username', passwd='password')

   # List files in the current directory
   ftp.retrlines('LIST')

   # Download a file
   with open('filename.txt', 'wb') as local_file:
       ftp.retrbinary('RETR filename.txt', local_file.write)

   # Upload a file
   with open('localfile.txt', 'rb') as local_file:
       ftp.storbinary('STOR localfile.txt', local_file)

   # Close the connection
   ftp.quit()
   ```