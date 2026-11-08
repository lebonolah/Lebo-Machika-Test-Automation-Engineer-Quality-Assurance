# Lebo-Machika-Test-Automation-Engineer-Quality-Assurance
Test automation portfolio: Playwright (JavaScript) UI tests in POM, BDD and data-driven styles, plus Swagger/OpenAPI API tests and Kafka event tests, with GitHub Actions CI.

# CWG QA Portfolio

Test automation portfolio built around a demo version of the **Crowned with Grace (CWG)** platform.
One system under test, five test projects, each structured differently on purpose.

| Project | Style | Tools | Folder |
|---|---|---|---|
| UI, Page Object Model | OOP (inheritance, fixtures) | Playwright + JavaScript | `tests/ui-pom` |
| UI, BDD | Gherkin features + step definitions | Playwright + playwright-bdd | `tests/ui-bdd` |
| UI, Data driven | Test rows in JSON | Playwright | `tests/ui-data-driven` |
| API, Swagger | API client layer, contract test, role matrix | Playwright request, OpenAPI | `tests/api-openapi` |
| Events | Kafka topic listener helper | kafkajs + Playwright runner | `tests/kafka-events` |

## Run it
```bash
npm install
npx playwright install chromium
npm run test:api          # API + Swagger contract
npm run test:ui:pom       # page objects
npm run test:ui:bdd       # Gherkin
npm run test:ui:data      # data driven

docker compose up -d kafka
KAFKA_BROKERS=localhost:9092 npm run app          # terminal 1
KAFKA_BROKERS=localhost:9092 npm run test:kafka   # terminal 2
```
Swagger UI: http://localhost:3000/api-docs (after `npm run app`).

See `docs/CICD.md` for the pipeline and `docs/ROADMAP.md` for the full platform plan.
Demo logins: admin@cwg.test / Admin#123, finance@cwg.test / Finance#123, coordinator@cwg.test / Coord#123.

