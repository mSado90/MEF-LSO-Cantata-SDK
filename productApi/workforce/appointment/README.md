# Appointment Management: Release notes

## Release Ella:

**Readiness status**: Requested Letter Ballot. It will be most likely published
as a standard without further changes.

**Summary** - The following updates introduced:

- added support for change MEF 113 :
  - added `inProgress` to `AppointmentStatusType`
- `get` operation in `/hub/{id}` endpoint added,
- API errors fixed

**appointmentManagement.api.yaml:**

- server URL : `https://{serverBase} mefApi/cantata/appointment/v1/` changed to
  `https://{serverBase}/mefApi/cantata/appointment/v2/`
- added operation
  - `/hub/{id}`
    - `get`
- `/appointment` endpoint
  - change return type to `Appointment_Find`
- modified types:
  - `AppointmentStatusType`
    - `inProgress` added
  - `Appointment`
    - set as required:
      - `id`
      - `relatedPlace`
      - `relatedContactInformation`
      - `status`
      - `validFor`
      - `workorder`
  - `Appointment_Create`
    - added:
      - `attachment`
      - `note`
      - `validFor`
    - set as required:
      - `relatedContactInformation`
      - `validFor`
      - `workOrder`
  - `Appointment_Create`
    - `relatedPlace` removed
  - `Appointment_Find`
    - `href` removed from required
  - `Appointment_Update`
    - `relatedPlace` added
  - `SearchTimeSlot`
    - `workOrder` added
    - `relatedEntity` removed
    - set as required:
      - `availableTimeSlot`
      - `workOrder`
      - `requestedTimeSlot`
  - `SearchTimeSlot_Create`
    - `workOrder` added
    - `relatedEntity` removed
    - set as required:
      - `workOrder`
      - `requestedTimeSlot`
  - `TimePeriod`
    - set as required:
      - `endDateTime`
      - `startDateTime`
- removed types:
  - `Error501`
  - `RelatedEntity`

**appointmentNotification.api.yaml:**

- server URL : `https://{serverBase}/mefApi/cantata/appointmentNotification/v1/`
  changed to `https://{serverBase}/mefApi/cantata/appointmentNotification/v2/`

## Release Dolly:

First release of this API.
