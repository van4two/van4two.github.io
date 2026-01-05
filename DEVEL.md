# Development

This project involves a Jekyll site and is configured to run inside a DevContainer for a consistent development environment.

## 1. Launch the DevContainer

To start developing, open this project in VS Code. You should see a notification to "Reopen in Container". If not, you can:

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
2. Run **Dev Containers: Reopen in Container**.

This will build the container and set up the environment.

### Dependencies

Dependencies are automatically handled. The `.devcontainer/post-create.sh` script runs automatically after the container is created. It installs specific Bundler versions and runs `bundle install` to ensure all Jekyll dependencies are ready.

## 2. Build and Serve the Site

You can run the site using either a VS Code Task or the command line.

### Option A: VS Code Task (Recommended)

1. Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`).
2. Run **Tasks: Run Task**.
3. Select **Jekyll Serve (with livereload)**.

This task runs `bundle exec jekyll serve --livereload --incremental --host 0.0.0.0`.

### Option B: Command Line

If you prefer the terminal, open a terminal inside the DevContainer and run:

```bash
bundle exec jekyll serve --livereload --host 0.0.0.0
```

## 3. Testing

Once the server is running, you can view the site locally at:

[http://localhost:4000](http://localhost:4000)


Live reload is enabled, so changes to files will automatically refresh the browser.

## 4. Troubleshooting

### Port not accessible?
If `localhost:4000` is not working, check the **Ports** view in VS Code (`Cmd+J` / `Ctrl+J` -> **Ports** tab).
- Ensure port **4000** is listed.
- If it's missing, click **Forward a Port** and enter `4000`.
- Ensure the "Forwarded Address" is `localhost:4000`.
