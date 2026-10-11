========================================================================

                 CAMUNDA 8 EVENT REGISTRATION PROJECT

========================================================================



PROJECT OVERVIEW

----------------

This repository contains a complete event registration workflow project built 

for Camunda 8 (Zeebe engine). It integrates an executable BPMN process model, 

a dynamic user task form schema, and a tasklist runtime preview.



REPOSITORY FILES

----------------

1. Ex4_EventRegistration.bpmn

   - BPMN 2.0 executable process model ("Event Registration Process").

   - Controls process flow, task assignment, and form linking.



2. form_2.form

   - JSON form schema ("Form_EventRegistration").

   - Renders the UI form for task reviewers inside Camunda Tasklist.



3. Untitled.png

   - Execution preview showing a completed task in Camunda Tasklist.





BUSINESS PROCESS ARCHITECTURE

-----------------------------

[ Submit Registration ] ---> [ Review Event Registration ] ---> [ Registration Processed ]

    (Start Event)                   (User Task)                      (End Event)



Process Flow Details:

  - Start Event: "Submit Registration" (ID: Start_SubmitReg)

  - User Task: "Review Event Registration" (ID: Task_ReviewReg)

      * Linked Form ID: Form_EventRegistration

      * Candidate Groups: camunda-admin, demo

  - End Event: "Registration Processed" (ID: End_Processed)





FORM SPECIFICATION (Form_EventRegistration)

-------------------------------------------

Field Label   | Key                 | Type      | Validation / Details

--------------+---------------------+-----------+-------------------------

Name          | attendeeName        | textfield | Required

Date          | eventDate           | textfield | Format: YYYY-MM-DD

Reason        | registrationReason  | textarea  | Optional details/notes





EXECUTION PREVIEW

-----------------

<img width="1232" height="698" alt="image" src="https://github.com/user-attachments/assets/e10a4cf7-cb6a-46d6-b5eb-a85bec01ab8d" />




Displays a completed "Review Event Registration" task with submitted attendee

data (Name: Vedika Choudhary, Date: 2026-10-30, Reason: High fever) within the

Camunda Tasklist UI.





DEPLOYMENT & RUNTIME INSTRUCTIONS

---------------------------------

1. Open Camunda Modeler (v5.0+ or Desktop/Web Modeler v5.49+).

2. Load "Ex4_EventRegistration.bpmn" and "form_2.form".

3. Deploy both process and form schemas to your Camunda 8 SaaS or local cluster.

4. Start an instance of process ID "EventRegistrationProcess".

5. Log into Camunda Tasklist as a user in "camunda-admin" or "demo" group.

6. Open "Review Event Registration", fill in details, and complete the task.



========================================================================
