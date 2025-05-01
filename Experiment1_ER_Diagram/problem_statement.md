# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.

# ER Diagram Submission - Harshini R
## Scenario Chosen: Hospital Database
## ER Diagram:
![image](https://github.com/user-attachments/assets/efa115ed-c843-4cb4-9d4c-0673155c2015)

## Entities and Attributes:

PATIENT  
- PatientID (PK)  
- FullName  
- DOB  
- Gender  
- PhoneNumber  
- Address  
- Email  
- InsuranceDetails  
DOCTOR  
- DoctorID (PK)  
- FullName  
- Specialization  
- PhoneNumber  
- Email  
- WorkSchedule  

APPOINTMENT  
- AppointmentID (PK)  
- AppointmentDate  
- AppointmentTime  
- ReasonForVisit  
- PatientID (FK)  
- DoctorID (FK)
   
EDICAL_RECORD  
- MedicalRecordID (PK)  
- PatientID (FK)  
- DoctorID (FK)  
- Diagnoses  
- PrescribedMedications  
- Treatments  
- TestResults  
- AdditionalNotes  

BILLING  
- BillingID (PK)  
- AppointmentID (FK)  
- Amount  
- PaymentDate  
- PaymentMethod  
- PaymentStatus  

DEPARTMENT  
- DepartmentID (PK)  
- DepartmentName  
- DepartmentHead  



## Relationships and Constraints:

Patient → Appointment = 1 patient, many appointments

Doctor → Appointment = 1 doctor, many appointments

Appointment → Prescription = 1 appointment, many prescriptions

Prescription → Medication = Many prescriptions can have same medication

Patient → Admission = 1 patient, many admissions

Room → Admission = 1 room, many admissions

Doctor → Department = Many doctors in 1 department

Constraints :
Primary Keys: Uniquely identify each row (PatientID, DoctorID, etc.)


Foreign Keys: Link between tables (e.g., Appointment has PatientID)

NOT NULL: Important fields can’t be empty

UNIQUE: For fields like emails or phone numbers

CHECK: Logic rules (like Age > 0, Dates make sense)

DEFAULT: Default values (e.g., Status = ‘Pending’)
...

## Extension (Prerequisite / Billing):

We modeled the billing process by associating each Admission with a Billing entity.

Each Admission generates a Bill that contains fields such as BillID, TotalAmount, PaidStatus, and PaymentDate.

The Billing table includes a foreign key referencing the AdmissionID, establishing a link between the bill and the corresponding patient admission.

An optional field like PaymentMode (e.g., UPI, Card, Cash) can be included for more detailed tracking.

We also modeled prerequisites for Appointments.

Certain Appointments may require specific prerequisite tests like Blood Test, X-Ray, etc.

These are captured using a separate Prerequisite table that links each AppointmentID with the necessary TestID(s).


## Design Choices:

Entities like Patient, Doctor, Room, Admission, and Prescription were selected to represent core elements in a hospital system.

Appointments and Admissions were treated as separate entities to distinguish between outpatient visits and inpatient admissions.

A separate Medication table allows multiple prescriptions to share the same medication and vice versa, supporting a many-to-many relationship.

Doctors are linked to Departments to reflect their specialization and work area.

Rooms are tied to Admissions to track where patients are accommodated.

Constraints such as Primary Key, Foreign Key, NOT NULL, UNIQUE, CHECK, and DEFAULT ensure data integrity and logical consistency.

All relationship cardinalities are modeled to accurately reflect real-life hospital workflow, like one doctor having many appointments, and one patient having multiple admissions.



## RESULT
A Database to the Hospital management is created succesfully
