<h1 align="center">Onyma Appointments :diamond_shape_with_a_dot_inside: </h1>

_This project have simple **CRUD** implementation, but a great and scalable architecture.
Before each commit and push, tests are automatically running to guarantee the project security_

### Get Starting

You should have [docker](https://www.docker.com/) instaled
You should have [firebase](https://console.firebase.google.com/) account and a real time data base running

- Clone the project:
```
git clone https://github.com/Luryy/Onyma-Appointments.git
cd Onyma-Appointments
```

- Create a **.env** file:
```
COPY the .env.example and fill the fields
```

- Create a docker image
```
docker build . -t onyma-appointments
```

- Finally Create your container
```
docker run -d --name onyma-appointments -p 3333:3333 onyma-appointments
```

### Usage

The aplicacation have 5 routes:


- **```GET /appointments```** - To list all of your appointments.
- **```GET /appointments/:id```** - To list an appointment by it id.
- **```POST /appointments```** - To create a new appointment - and in return the appointment created.
- **```POST /appointments/:id```** - To edit an existent appointment by it id - and in return the appointment updated. It's possibly to update only one params.
- **```DELETE /appointments/:id```** - To delete an appointment by it id.

**```POST params:```**
```json
{
  "address": "Maceió",
  "patientName": "Lucas",
  "dateTime": "22h40",
  "state": "scheduled"
}
```


### Projec Structure

Here is the project structure:

```
.
├── src
│   ├── modules
│   │   └── appointments
│   │       ├── container
│   │       │   └── index.ts
│   │       ├── dtos
│   │       │   ├── IAppointmentDTO.ts
│   │       │   ├── ICreateAppointmentDTO.ts
│   │       │   └── IUpdateAppointmentDTO.ts
│   │       ├── infra
│   │       │   ├── firebase
│   │       │   │   ├── models
│   │       │   │   │   └── Appointment.ts
│   │       │   │   └── repositories
│   │       │   │       └── AppointmentsRepository.ts
│   │       │   └── http
│   │       │       ├── controllers
│   │       │       │   └── AppointmentsController.ts
│   │       │       └── routes
│   │       │           └── appointments.routes.ts
│   │       ├── repositories
│   │       │   ├── fakes
│   │       │   │   └── FakeAppointmentsRepository.ts
│   │       │   └── IAppointmentsRepository.ts
│   │       └── useCases
│   │           ├── CreateAppointment
│   │           │   ├── CreateAppointmentUseCase.spec.ts
│   │           │   └── CreateAppointmentUseCase.ts
│   │           ├── DeleteAppointment
│   │           │   ├── DeleteAppointmentUseCase.spec.ts
│   │           │   └── DeleteAppointmentUseCase.ts
│   │           ├── ListAppointments
│   │           │   ├── ListAppointmentsUseCase.spec.ts
│   │           │   └── ListAppointmentUseCase.ts
│   │           ├── ShowAppointment
│   │           │   ├── ShowAppointmentUseCase.spec.ts
│   │           │   └── ShowAppointmentUseCase.ts
│   │           └── UpdateAppointment
│   │               ├── UpdateAppointmentUseCase.spec.ts
│   │               └── UpdateAppointmentUseCase.ts
│   └── shared
│       ├── container
│       │   └── index.ts
│       ├── helpers
│       │   └── types
│       │       └── PartialRequireOne.ts
│       └── infra
│           ├── firebase
│           │   └── index.ts
│           └── http
│               ├── app.ts
│               ├── middlewares
│               │   └── rateLimiter.ts
│               ├── routes
│               │   └── index.ts
│               └── server.ts
├── babel.config.js
├── Dockerfile
├── heroku.yml
├── jest.config.js
├── LICENSE
├── package.json
├── prettier.config.js
├── README.md
├── tsconfig.json
└── yarn.lock
```
This project is based at **Domain-driven design**.

At folder models is where your domains should be, and the commons configurations should be at the shared folder.

##### Folders
* **container** - where you register dependency injection
* **dtos** - define transfer objects
* **infra** - external services - should use interfaces and dependency injection for decoupling purpose
* **repositories** - repository interface and fake (for tests)
* **useCases** - where shoud be the business rule of your application | remember to create unit tests!




To a better understanding you should open the files and see yours responsabilities.

## :pushpin: Technologies:
- [Docker](https://www.docker.com/)
- [Express](https://expressjs.com/)
- [Firebase](https://console.firebase.google.com/)
- [Jest](https://jestjs.io/)
- [Rate-Limiter](https://www.npmjs.com/package/rate-limiter-flexible)
- [Tsyringe](https://github.com/microsoft/tsyringe)
- [Typescript](https://www.typescriptlang.org/)


## Autor

👤 **Lucas Yuri**

- Github: [Luryy](https://github.com/luryy)
- LinkedIn: [Lucas Yuri](https://linkedin.com/in/lucas-yuri)


## 📝 License

Copyright © 2020 [Lucas Yuri](https://github.com/luryy).
This project is [MIT](LICENSE) licensed.

