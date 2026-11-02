# 07 — Database Applications

**VU CS403 handout:** Lectures 32–34

This section covers application programs and user interfaces through which people interact with a database.

## 1. Database and application

The DBMS stores and manages data. The application provides user workflows such as adding a student, registering a student in a course, searching for a result, or producing a transcript.

The application should validate input and guide users. Database constraints remain important because data may be changed through more than one application path.

## 2. User interface design

The handout discusses interfaces for users with different experience levels and gives usability guidance. A usable interface should:
- Make actions easy to discover.
- Use consistent controls and terminology.
- Help users understand the current task.
- Reduce unnecessary memory burden.
- Be designed around the user's process rather than exposing raw database structures.

## 3. Forms and controls

A form is a user-facing way to enter, view, or edit related information. Controls may include text boxes, buttons, checkboxes, and date fields.

Example: a course registration form may contain student registration number, course selection, semester, and a submit button.

The form should make required fields clear and prevent obviously invalid input. The application must still handle database errors such as duplicate registrations or invalid references.

## Practice

Sketch a course-registration form. Label its fields, identify required input, describe validation, and explain what should happen if the student is already registered.

## Next
[08 — Storage and Indexing](../08-storage-and-indexing/README.md).
