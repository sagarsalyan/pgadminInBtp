How to create PostGre Admin in SAP BTP ?
Step 1 - Create a folder with any name, e.g. pgadmin
Step 2 - Create a file called manifest.yml and add content (content is in manifest.yml)
        applications:
        - name: pgadmin-web
        instances: 1
        memory: 1G
        disk_quota: 1G
        health-check-type: process
        docker:
            image: dpage/pgadmin4:2023-05-02-1
        random-route: true
        env:
            PGADMIN_DEFAULT_EMAIL: Admin@Email.com
            PGADMIN_DEFAULT_PASSWORD: Admin
            PGADMIN_LISTEN_ADDRESS: 0.0.0.0
Step 3 - Run comman 'cf deploy manifest.yml' or 'cf deploy -f manifest.yml'