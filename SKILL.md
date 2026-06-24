---
description: Test
---

# Instructions
Create a file named "index.html" with custom HTML and CSS code.
You must create a dashboard.
The dashboard is displayed in an iframe. Therefore, make sure it fills the entire screen and do not add a border or shadow.
When the page loads, you will recive Information listed under Incoming Information.

# Incoming Information
## Usage
```
window.addEventListener('message', event => {
    // event.data contains the contact data
    const contact = event.data.contact;
    const user = event.data.user;
});
```

## Examples
Its not guaranted that all of those fields are having data.

user.displayName (String) - Name of the requesting user.
user.userPrincipalName (String) - Unique login identifier of the requesting user. E-Mail Address

contact.entryId (String) - Unique identifier of the contact.
contact.entryDn (String) - Distinguished Name from a directory service added in the VDir.
contact.dataSource (String) - Source system of the contact data.

contact.personal.name.fullName (String) - Complete name.
contact.personal.name.firstName (String) - Given name.
contact.personal.name.lastName (String) - Family name.
contact.personal.name.title (String) - Honorific or professional title.
contact.personal.name.displayName (String) - Preferred display name.

contact.personal.birthday (Date String) - Date of birth.

contact.personal.address.street (String) - Street address.
contact.personal.address.city (String) - City name.
contact.personal.address.postalCode (String) - Postal/ZIP code.
contact.personal.address.country (String) - Country name.

contact.phoneNumbers.work (Array<String>) - Business phone numbers.
contact.phoneNumbers.mobile (String) - Mobile phone number.
contact.phoneNumbers.home (String) - Home phone number.
contact.phoneNumbers.faxNumbers (Array<String>) - Fax numbers.

contact.emails.primary (String) - Primary email address.
contact.emails.work (Array<String>) - Additional work email addresses.

contact.company.name (String) - Company name.
contact.company.employmentInfo (String) - Job title or role.
contact.company.department (String) - Organizational department.
contact.company.website (URL String) - Company website.

contact.company.address.street (String) - Company street address.
contact.company.address.city (String) - Company city.
contact.company.address.postalCode (String) - Company postal code.
contact.company.address.country (String) - Company country.

contact.customFields.custom1-custom20 (String) - Organization-specific custom metadata fields.

contact.dbFields.dbAppVersion (String) - Source application version.
contact.dbFields.dbApplication (String) - Source application name.
contact.dbFields.dbDataBase (String) - Source database name.
contact.dbFields.dbEntityType (String) - Database entity type.
contact.dbFields.dbInstance (String) - Database instance identifier.
contact.dbFields.dbNativeId (String) - Native source-system identifier.
contact.dbFields.dbParentId (String) - Parent entity identifier.
contact.dbFields.dbServer (String) - Database server identifier.

contact.thumbnailUrl (String) - Profile image URL or Data URI.
contact.contactType (String) - Contact category/type.
contact.isObscured (Boolean) - Indicates whether data is masked or hidden.

# Outgoing Information
## Usage
```
window.addEventListener('message', event => {
    // event.data enthält die Kontaktdaten
    const contact = event.data.contact;
    const user = event.data.user;
});
```

## Exampels
The Default Clipboard dont works cause of security standarts. So use this instead: { "type": "copyText", "value": "Zu kopierender Text" }
Refresh the contained data: { "type": "refresh" }
Open an Mail (mailto): { "type": "sendEmail", "value": "benutzer@ventureprise.com" }
Start an Call: { "type": "callPhoneNumber", "value": "+4917612345678" }

# Required Informations
Before you start building, be sure that you have all those informationos. If some of them are missing, ask the user before you start!
- How should the Dashboard look like?
- Which Informations should be displayed?

# Other Sources and Examples:
- https://help.c4b.com/cbyx/de/admin/intgrtn/insights.html
- https://github.com/C4BAG/insights-examples