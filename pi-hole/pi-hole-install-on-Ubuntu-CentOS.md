### Installing Pi-hole on Linux (Ubuntu and CentOS)

Pi-hole can be installed on various Linux distributions, including Ubuntu and CentOS. Below are the steps for installing Pi-hole on each.

#### **Installation on Ubuntu**

1. **Update Your System**:
   Begin by updating your system’s package list and installing any available updates.
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```

2. **Install Required Dependencies**:
   Ensure that curl is installed, which is needed to download the Pi-hole installation script.
   ```bash
   sudo apt install curl -y
   ```

3. **Download and Run the Pi-hole Installation Script**:
   Pi-hole provides a simple installation script that takes care of most of the setup. Run the following command:
   ```bash
   curl -sSL https://install.pi-hole.net | bash
   ```
   - This command will download and execute the Pi-hole installation script.
   - Follow the on-screen prompts during installation to configure Pi-hole according to your preferences.

4. **Configure Pi-hole**:
   - During the installation, you will be prompted to select the upstream DNS provider (e.g., Google, OpenDNS).
   - Choose which blocklists to include.
   - You will also need to configure your network settings, such as whether to use Pi-hole as your DHCP server.

5. **Access the Pi-hole Admin Interface**:
   Once installed, you can access the Pi-hole web interface to manage settings and monitor activity.
   ```bash
   http://<your-pi-hole-ip-address>/admin/
   ```
   - The default admin password is displayed at the end of the installation. You can change it using:
   ```bash
   pihole -a -p
   ```

6. **Set Up Pi-hole as the DNS Server on Your Router**:
   To use Pi-hole across your entire network, configure your router to use Pi-hole as its DNS server. This is typically done in the DNS settings of your router's admin interface.

#### **Installation on CentOS**

1. **Update Your System**:
   Update your CentOS system before installing Pi-hole.
   ```bash
   sudo yum update -y
   ```

2. **Install Required Dependencies**:
   Install the necessary dependencies such as `curl`.
   ```bash
   sudo yum install curl -y
   ```

3. **Download and Run the Pi-hole Installation Script**:
   Use the following command to download and execute the Pi-hole installation script:
   ```bash
   curl -sSL https://install.pi-hole.net | bash
   ```
   - Similar to the Ubuntu installation, the script will guide you through the process.

4. **Configure Pi-hole**:
   - Follow the prompts to configure your DNS provider, blocklists, and network settings.

5. **Access the Pi-hole Admin Interface**:
   After installation, you can access the Pi-hole admin interface in the same way:
   ```bash
   http://<your-pi-hole-ip-address>/admin/
   ```

6. **Configure Your Network**:
   To ensure all devices on your network use Pi-hole, set it as the DNS server in your router’s settings.

#### **Post-Installation Steps for Both Ubuntu and CentOS**

- **Update Pi-hole**:
  Keep Pi-hole updated with the latest versions of the software and blocklists.
  ```bash
  pihole -up
  ```

- **Whitelisting and Blacklisting Domains**:
  Manage domains manually using the web interface or through the command line.
  - To whitelist a domain:
  ```bash
  pihole -w example.com
  ```
  - To blacklist a domain:
  ```bash
  pihole -b ads.example.com
  ```

- **Log Management**:
  Manage logs to ensure Pi-hole doesn't consume too much disk space:
  ```bash
  pihole -f
  ```

These steps cover the installation process for Pi-hole on both Ubuntu and CentOS, providing a solid foundation to start blocking ads and protecting privacy on your network.
