# Solution for Linux

## Cloning the Project and Running via npm

1. Clone the project repository:
   ```sh
   git clone https://github.com/Ahassan1995/TWS_HACKATHON_ABDULLAH_HASSAN.git
   ```
2. Navigate into the project directory:
   ```sh
   cd TWS_HACKATHON_ABDULLAH_HASSAN
   ```
3. Install dependencies:
   ```sh
   npm install
   ```
4. Run the project:
   ```sh
   npm run dev
   ```

## Creating a User and Restricting npm Execution

1. Create a new user:
   ```sh
   sudo adduser dev
   sudo groupadd editors
   sudo usermod -aG editors dev
   ```

2. Set a password for the new user:
   ```sh
   sudo passwd dev
   ```

3. Restrict execution of `npm` for the user:
   ```sh
   sudo chown -R ubuntu:editors /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN
   sudo find /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN -type d -exec chmod 770 {} ;
   sudo find /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN -type f -exec chmod 660 {} ;

   sudo chmod 750 /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN/node_modules/.bin/vite
   sudo chmod 750 /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN/package.json
   sudo chmod 750 /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN/package-lock.json

   ```

4. Further restrict access to the project’s `dev` script:
   ```sh
   sudo chmod -R 750 /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN
   sudo chown ubuntu:dev /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN/package.json
   sudo chmod 640 /home/ubuntu/TWS_HACKATHON_ABDULLAH_HASSAN/package.json
   ```


Now, `dev` can access the system but cannot execute `npm` commands to run the project.

![Image](https://github.com/user-attachments/assets/067cf14a-87b4-4718-bef5-31c07c14b6be)