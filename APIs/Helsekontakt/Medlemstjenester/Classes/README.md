# Classes

FHIR resource snippets for Medlemstjenester (health offerings and member lists).

- [HealthcareService.mmd](HealthcareService.mmd) – Offered service

```mermaid
classDiagram
class HealthcareService {
	+string identifier
	+bool active
	+string name
	+string comment
	+Reference providedBy
	+Reference location
	+Endpoint endpoint
}

```

- [Organization.mmd](Organization.mmd) – Providing organization

```mermaid
classDiagram
class Organization {
	+string identifier
	+string name
	+Endpoint endpoint
}

```

- [Location.mmd](Location.mmd) – Service location

```mermaid
classDiagram
class Location {
	+Address address
	+Telecom[] telecom
}

```

- [Endpoint.mmd](Endpoint.mmd) – Communication endpoint

```mermaid
classDiagram
class Endpoint {
	+string identifier
	+string id
}

```

- [Address.mmd](Address.mmd) – Postal address

```mermaid
classDiagram
class Address {
	+string line
	+string city
	+string postalCode
}

```

- [Telecom.mmd](Telecom.mmd) – Contact points

```mermaid
classDiagram
class Telecom {
	+string system
	+string value
}

```

- [Patient.mmd](Patient.mmd) – Member record

```mermaid
classDiagram
class Patient {
	+string identifier
	+Contact contact
}

```

- [Contact.mmd](Contact.mmd) – Member contact linkage

```mermaid
classDiagram
class Contact {
	+Reference organization
	+Period period
}

```

- [Period.mmd](Period.mmd) – Service period

```mermaid
classDiagram
class Period {
	+date start
	+date end
}

```

## Identifier notes and XML examples

- `Endpoint.identifier`: For communication endpoints the PDF shows a HER-id identifier is used. Example system/OID used in examples: `urn:oid:2.16.578.1.12.4.1.2` with a numeric HER-id value (often HER level 2 for service endpoints). Use this to populate `Endpoint.identifier.system` and `Endpoint.identifier.value` when sending `HealthcareService`.

Example (excerpt):

```xml
<endpoint>
	<identifier>
		<system value="urn:oid:2.16.578.1.12.4.1.2"/> <!-- HER-id -->
		<value value="129688"/>
	</identifier>
</endpoint>
```

- `Organization.identifier`: Organization identifiers are shown in examples with system `urn:oid:2.16.578.1.12.4.1.4.101` (organisation number) or similar OIDs; use these to link `HealthcareService.providedBy` and `Patient.contact.organization`.

Example (excerpt):

```xml
<Organization>
	<identifier>
		<system value="urn:oid:2.16.578.1.12.4.1.4.101"/>
		<value value="948554062"/>
	</identifier>
</Organization>
```

- `Patient.identifier`: Use national person identifier as shown in examples (system `urn:oid:2.16.578.1.12.4.1.4.1`).

Example (excerpt):

```xml
<Patient>
	<identifier>
		<system value="urn:oid:2.16.578.1.12.4.1.4.1"/> <!-- fødselsnummer/d-nummer -->
		<value value="13116900216"/>
	</identifier>
</Patient>
```
