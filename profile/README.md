# Medha

**Medha** is an AI-powered system to run a university department: courses, attendance, exams, marking and results.

> "Medha" is a working name. It may change before public launch.

## Who it is for

- **Teachers** — set up courses, take attendance, make questions, run online/offline exams, mark scripts with AI help, and make result cards.
- **Students** — join courses, take exams, and see marks and attendance.
- **Admin (department office)** — set up semesters and users, assign courses, approve and publish results.

## Main ideas

- AI helps in every part of the work, but **a teacher always makes the final decision**.
- Built as **microservices**, one repository per service.
- Requirements are tracked with IDs (for example `FR-T-10`) from the [SRS](https://github.com/medha-dms/medha-docs/blob/main/srs.md) to Jira stories, code and tests.

## Repositories

| Repository | What it holds |
| --- | --- |
| [medha-docs](https://github.com/medha-dms/medha-docs) | SRS, architecture decisions (ADR), service list, guides |
| `web` | Frontend (coming soon) |
| `api-gateway` | Single entry point for all requests (coming soon) |
| `identity-service` | Login, users, roles (coming soon) |
| `academic-service` | Semesters, batches, courses, enrolment (coming soon) |
| `assessment-service` | Marking policy, attendance, marks, results (coming soon) |
| `infra` | Docker Compose, CI templates, deploy config (coming soon) |

## Contributing

Read the [contributing guide](https://github.com/medha-dms/.github/blob/main/CONTRIBUTING.md) before you open a pull request.
