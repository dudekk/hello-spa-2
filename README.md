# HelloSpa

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 9.1.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

### Docker build

Run `docker build . --file docker/Dockerfile --tag hello-spa:$(date +%s)` to build application using docker.  
It produces a docker image with exposed port `80`, where application content is served.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Vagrant provisioning

Run `vagrant up` to start virtual machine which [Vagrant](https://vagrantup.com) will automatically provision building Docker image. You should see the output from the shell script appear in your terminal.

Before execution you should consider changing values of available resources for virtual machine corresponding your hardware resources.

```
v.memory = 4096
v.cpus = 2
```

After successful execution you should see following terminal output:

```==> default: Mounting shared folders...
    default: /vagrant => /root/sant-travis/hello-spa-2-master
==> default: Running provisioner: docker...
    default: Installing Docker onto machine...
==> default: Starting Docker containers...
==> default: -- Container: dudekk/hello-spa
```

Vagrantfile is configured using port-forward to allow connecting to the web server so you should be able to access it from the host machine on port 8081 `localhost:8081` 

If the guest machine is already running from the previous step, run `vagrant reload --provision`, which will quickly restart your virtual machine, skipping the initial import step. The provision flag on the reload command instructs Vagrant to run the provisioners, since usually Vagrant will only do this on the first `vagrant up`.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
