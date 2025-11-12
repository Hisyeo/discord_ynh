## Deploying to YunoHost

This application is designed to be deployed on a YunoHost server using the `my_webapp` package.

### Installation

1.  Connect to your server via SSH.
2.  Clone this repository: `git clone https://github.com/Hisyeo/DiscordBot.git -b yunohost`
3.  Navigate to the cloned directory: `cd DiscordBot`
4.  Run the YunoHost installation command:

    ```bash
    sudo yunohost app install . --args "domain=your_domain.tld&path=/bot&user=hisyeo-bot&app_name=hisyeo-discord-bot&app_repo=https://github.com/Hisyeo/DiscordBot.git&app_branch=a-new-hope&app_launch_command=npm start&app_port=3000&is_public=true"
    ```

    Replace `your_domain.tld` with your actual domain.

### Configuration

The application requires the following environment variables to be set in the `.env` file:

*   `PUBLIC_KEY`: Your Discord application's public key.
*   `APP_ID`: Your Discord application's ID.
*   `TOKEN`: Your Discord bot's token.

You can set these variables using the following command:

```bash
sudo yunohost app shell hisyeo-abugida-bot --script "echo 'PUBLIC_KEY=your_public_key' > .env"
sudo yunohost app shell hisyeo-abugida-bot --script "echo 'APP_ID=your_app_id' >> .env"
sudo yunohost app shell hisyeo-abugida-bot --script "echo 'TOKEN=your_token' >> .env"
```

Replace `your_public_key`, `your_app_id`, and `your_token` with your actual credentials.

### Starting the Application

The application should start automatically after installation. If you need to start it manually, you can use the following command:

```bash
sudo yunohost app service hisyeo-abugida-bot start
```