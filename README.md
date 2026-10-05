# Switchly API

A feature flag management API built with Java and Spring Boot. Flags are organized as **Organization → Project → Flag**, and each flag can be turned on or off.

## Tech stack
- Java, Spring Boot, Maven
- REST API with validation and error handling (400, 404, 409)
- In-memory storage

## Run locally
```bash
git clone https://github.com/deepanshuguptacse2024-create/SwitchlyApiApplication.git
cd SwitchlyApiApplication
./mvnw spring-boot:run
```
Server starts on `http://localhost:8080`.

## API endpoints

| Method | Path | Description |
|---|---|---|
| POST | `/api/v1/orgs` | Create a Organization |
| GET | ` /api/v1/orgs ` | list of organization |
| GET | `/api/v1/orgs/{orgsId}` | Get one Organization |
| POST | `/api/v1/orgs/{orgsId}/projects` | create a projects|
| GET | `/api/v1/projects/{projectId} ` | Get one projects |
| POST | `/api/v1/projects/{projectId}/flags` | Create a flag |
| GET | `/api/v1/projects/{projectId}/flags` | List flags of a project |
| PUT | `/api/v1/flag/{flagId}/state` | Turn a flag on/off |


## Create a Organization
Request Body in Json Formate:
{ 
"name": " apple" 
}
organizations is apple 

### Create a flag
Request body:
```json
{
  "key": "new-dashboard",
  "name": "New dashboard",
  "description": "Optional note about the flag"
}
```
- `key`: required, only lowercase letters, numbers and hyphens
- `name`: required
- `description`: optional

Response: `201 Created`

## Error responses
| Status | When |
|---|---|
| 400 | Invalid input (blank name, bad key format) |
| 404 | Project or flag not found |
| 409 | Flag key already exists in the project |

## Screenshots

### Create organization
screenshot of working api 
<img width="1232" height="656" alt="Screenshot 2026-10-05 165717_edited" src="https://github.com/user-attachments/assets/9f79fd1f-16a2-4aa0-8c0b-03fe259864fc" />
### list one organization
screenshort of working api 
<img width="1280" height="707" alt="Screenshot 2026-10-05 165742" src="https://github.com/user-attachments/assets/fe3d793f-be2e-4cce-a161-7d64d19d64b3" />
### create project in organization 
example project is : { Reparing}
screenshort of working api 
<img width="1268" height="763" alt="Screenshot 2026-10-05 170309" src="https://github.com/user-attachments/assets/26e9ca3b-79ec-4697-9195-f871e62201ea" />
### list of one project in organization 
screen shot of this working api 
<img width="1271" height="760" alt="Screenshot 2026-10-05 170347" src="https://github.com/user-attachments/assets/f98a6698-6396-4e68-a90f-0035ef498fc2" />
### create a flag 
<img width="1237" height="751" alt="Screenshot 2026-10-05 170936" src="https://github.com/user-attachments/assets/65163a7f-5549-4483-8331-eca39c5e1ac6" />
### Get one flag 
<img width="1281" height="792" alt="Screenshot 2026-10-05 171016" src="https://github.com/user-attachments/assets/bb738fce-311d-4886-8fe3-2367858204e6" />
### Turn flag on/off
<img width="1193" height="652" alt="Screenshot 2026-10-05 171401" src="https://github.com/user-attachments/assets/d9fb5e91-d697-4b3a-861f-33d78eb72ec3" />
