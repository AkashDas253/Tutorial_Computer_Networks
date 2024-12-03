### Example FTP Session Using Command Prompt

1. **Open Command Prompt**:
   - Press `Win + R`, type `cmd`, and press `Enter`.

2. **Connect to Server**:
   ```plaintext
   ftp ftp.example.com
   ```

3. **Login**:
   ```plaintext
   Name (ftp.example.com:username): user
   Password: *****
   ```

4. **List Files**:
   ```plaintext
   ls
   ```

5. **Download File**:
   ```plaintext
   get filename.txt
   ```

6. **Upload File**:
   ```plaintext
   put localfile.txt
   ```

7. **Close Connection**:
   ```plaintext
   bye
   ```