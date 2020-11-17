# Laravel setup

## Create a Laravel application

1. In the Application section click the Create application button

2. Choose the virtual machine where you want it deployed

3. Select Laravel from the Framework tab

4. Provide a meaninful name

5. Click Create Application

## Create a custom deployment

1. Add a custom repository in your organization or connect your git account

- Type in the name of the repository
- Select the repository type: Public or Private
- Set the repository address in the remote url field

2. Create a new deployment

- Deploy Path on server/s - take the path from the Overview section of the application you just installed
- Application user - the ftp username in the Overview section of the application you just installed

3. Select the deployment servers

4. Configure the application secrets

Deployment config file sample

```
.env.example
```

Deployment config file

```
.env
```

Deployment config file format

```
bash
```

Generate APP_KEY

```
php artisan key:generate --show
```

5. Add deploy steps



