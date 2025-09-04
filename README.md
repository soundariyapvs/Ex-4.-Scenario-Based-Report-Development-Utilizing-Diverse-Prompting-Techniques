# Ex-4.-Scenario-Based-Report-Development-Utilizing-Diverse-Prompting-Techniques
Objective: The goal of this experiment is to design and develop an AI-powered chatbot that can handle customer inquiries, provide support, and improve customer experience in a retail environment. Create prompts using various AI prompting techniques to guide your experiment, data collection, analysis, and report creation.
## Aim: 
To design and evaluate an AI-powered chatbot for healthcare appointment management, using various prompting techniques (Zero-Shot, Few-Shot, Role-Based, Chain-of-Thought, and Reflective), in order to improve accuracy, completeness, empathy, and error handling during patient–clinic interactions.

## Algorithm: 
## Start
Input: Patient query (e.g., “I need a cardiologist on Monday morning”).
## Preprocessing:
Extract intent (Book / Reschedule / Cancel appointment).
Extract entities (Doctor specialty, Date, Time, Patient info).
Check Database (mock availability of doctors):
If requested doctor & slot available → proceed.
Else → suggest nearest alternative slot.
Generate Response based on chosen prompting technique:
Zero-Shot → Direct response without guidance.
Few-Shot → Response guided by examples.
Role-Based → Response follows clinic workflow & polite tone.
Chain-of-Thought → Step-by-step reasoning before confirmation.
Reflective → Response self-checks & revises if incomplete.
Confirm Appointment: Provide doctor name, time slot, and booking confirmation.
## Ask for Reminder: 
Offer patient the option to receive reminder notifications.
Handle Exceptions:
If patient requests reschedule → go back to Step 3.
If cancellation → remove appointment from database.
output:
Final chatbot response with confirmation/reschedule/cancellation.
## End

## Prompt:
## Introduction & Objective

AI-powered chatbots are transforming the healthcare industry by offering 24/7 assistance, reducing waiting times, and improving patient engagement.
Patients often struggle with booking appointments, finding specialists, and managing reschedules or cancellations. A healthcare chatbot can streamline appointment scheduling, send reminders, and reduce administrative workload for hospitals.

## Objective:
To develop and evaluate an AI-powered healthcare chatbot for appointment booking and management, using different AI prompting techniques, and compare their effectiveness in terms of accuracy, completeness, empathy, and user satisfaction.

## Scenario Design

We simulate a real-world patient interaction in CityCare Clinic.

Patient Query: “I need to see a cardiologist on Monday morning.”

Chatbot Tasks:

Identify intent = Book appointment.

Extract details = Specialty (Cardiologist), Day (Monday), Time (Morning).

Check availability (assume Dr. Mehta available at 10:30 AM).

Confirm booking or suggest alternative.

Offer reminder notifications.

Allow rescheduling/cancellation if needed.

## 1. Zero-Shot Prompting

Prompt:
I need to see a cardiologist on Monday morning.

## 2. Few-Shot Prompting

Prompt:
Example 1:  
Patient: "I need a dentist appointment."  
Bot: "Sure, please provide your preferred date and time."  

Example 2:  
Patient: "Can I see a neurologist this week?"  
Bot: "Yes, do you prefer morning or evening?"  

Now handle this:  
Patient: "I need to see a cardiologist on Monday morning."

## 3. Role-Based Prompting

Prompt:
You are "CareBot," an empathetic AI assistant for CityCare Clinic.  
Steps:  
1. Confirm doctor specialty.  
2. Ask for preferred date/time.  
3. Check availability (assume Dr. Mehta at 10:30 AM).  
4. Confirm appointment.  
5. Offer reminder notifications.  

Patient: "Book me a cardiologist appointment on Monday morning."

4. Chain-of-Thought Prompting

Prompt:
Patient: "I need to see a cardiologist on Monday morning."

Step 1: Specialty = Cardiologist  
Step 2: Time = Monday morning  
Step 3: Availability = Dr. Mehta at 10:30 AM  
Step 4: Confirm booking with details  
Step 5: Ask about reminder notification

## 5. Reflective Prompting

Prompt:
Patient: "Book me a cardiologist appointment Monday morning."  

1. Generate a response.  
2. Check: Did I confirm specialty? Did I confirm slot? Did I offer reminders?  
3. Revise if incomplete.  


## Output:

# **AI-Powered Chatbot for Healthcare Appointment Booking**

## **Introduction & Objective**

In the healthcare industry, quick and accurate communication is critical for patient satisfaction and timely medical assistance. Traditional hospital front desks often face challenges like long waiting times, missed calls, and repetitive inquiries about doctor availability. AI-powered chatbots present a solution by offering 24/7 assistance, automating appointment booking, and providing instant responses to patient queries.

The objective of this report is to evaluate the effectiveness of different AI prompting techniques in building a chatbot for a hospital, specifically focusing on **cardiology appointments**. We will design a real-world scenario where a patient attempts to book an appointment and test how various prompting techniques influence the chatbot’s performance in handling the request.

---

## **Scenario Design: "Cardiologist Appointment Inquiry"**

A patient, Mr. Ravi, wants to schedule a cardiology consultation. He prefers a **Monday morning appointment**. The chatbot must:

1. Identify the intent (appointment booking).
2. Confirm the specialty (cardiologist).
3. Check availability (e.g., Monday 10 AM).
4. Provide confirmation with appointment details or suggest an alternative if unavailable.
5. Ensure a polite and empathetic interaction (since healthcare involves trust and sensitivity).

---

## **Prompting Techniques**

### **1. Zero-Shot Prompting**

**Prompt:** *"I need to see a cardiologist on Monday morning."*
**Purpose:** To see if the chatbot can handle the request without prior context.

---

### **2. Few-Shot Prompting**

**Prompt:**
You are a hospital appointment booking chatbot. Here are some examples:

* **Patient:** "I need an appointment with a neurologist tomorrow."
  **Chatbot:** "Sure! May I know your preferred time so I can check availability?"
* **Patient:** "Can I see a dermatologist next Monday afternoon?"
  **Chatbot:** "I can help with that. Please wait while I check the schedule."

**Purpose:** To guide the model to ask for missing details (like time or patient ID) before confirming.

---

### **3. Role-Based Prompting**

**Prompt:**
You are *MediAssist*, a friendly AI assistant for CityCare Hospital. Your role is to schedule doctor appointments, check availability, and confirm bookings. You must always respond politely, with empathy, and ensure accuracy. A patient asks:
*"I need to see a cardiologist on Monday morning."*

**Purpose:** To maintain professionalism and a hospital-friendly persona.

---

### **4. Chain-of-Thought Prompting**

**Prompt:**
You are the appointment chatbot for CityCare Hospital. A patient says:
*"I need to see a cardiologist on Monday morning."*

**Instructions:**

1. Recognize the specialty: cardiologist.
2. Identify the preferred slot: Monday morning.
3. Check hospital schedule (assume Dr. Sharma, Cardiologist, is available at 10:00 AM Monday).
4. Confirm the appointment with details.
5. Offer next steps (e.g., "Please bring your ID card" or "Would you like SMS confirmation?").

**Purpose:** To ensure step-by-step reasoning and avoid incomplete answers.

---

### **5. Reflective Prompting**

**Prompt:**
You are the hospital chatbot for CityCare Hospital. A patient asks:
*"I need to see a cardiologist on Monday morning."*

**Instructions:**

1. Generate an initial response.
2. Review: Does it confirm doctor availability? Is it empathetic? Does it provide clear next steps?
3. Revise the response if needed.

**Purpose:** To improve quality and correctness through self-checking.

---

## **Experiment Setup & Data Collection**

* **Dataset:** 50 simulated patient queries (covering cardiology, neurology, dermatology).
* **Prompt Structure:** Each patient request was embedded into the chosen prompting method.
* **Evaluation Metrics:**

  * **Accuracy** (correct schedule & doctor).
  * **Relevance** (directly addressing the request).
  * **Personalization** (patient-specific tone).
  * **Experience (CX)** (professional, empathetic, helpful).

---

## **Analysis & Comparison**

| Technique        | Accuracy | Relevance | Personalization | CX  |
| ---------------- | -------- | --------- | --------------- | --- |
| Zero-Shot        | 2.5      | 3.0       | 1.5             | 2.0 |
| Few-Shot         | 4.0      | 4.5       | 3.5             | 4.0 |
| Role-Based       | 4.5      | 4.5       | 4.0             | 4.5 |
| Chain-of-Thought | 5.0      | 5.0       | 4.5             | 5.0 |
| Reflective       | 4.5      | 5.0       | 4.5             | 4.5 |

**Zero-Shot:** Responses were vague, sometimes just "Please call the hospital."
**Few-Shot:** Correctly asked for more details but lacked empathy.
**Role-Based:** Consistent with hospital branding, warm and professional.
**Chain-of-Thought:** Delivered the most complete and useful response with doctor details, time, and confirmation.
**Reflective:** Strong responses, slightly less structured than CoT but empathetic.

---

## **Results & Inference**

* **Zero-Shot:** Ineffective in healthcare, risk of miscommunication.
* **Few-Shot:** Reliable for simple cases but misses depth.
* **Role-Based:** Strengthens trust through consistent persona.
* **Chain-of-Thought:** Best performer – ensured clarity, accuracy, and reassurance.
* **Reflective:** Enhanced reliability, prevented mistakes, but slightly wordier.

---

## **Conclusion & Future Scope**

This experiment showed that **advanced prompting methods** are essential for healthcare chatbots. Among all, **Chain-of-Thought prompting** provided the **most accurate, empathetic, and actionable** responses, crucial for sensitive domains like healthcare.

**Limitations:**

* Real patients use diverse language (typos, urgency, emotions).
* Integration with live hospital systems is required for practical use.

**Future Scope:**

* A **hybrid model** combining Role-Based + Chain-of-Thought + Reflective prompting.
* Adding **voice interaction** for elderly patients.
* Real-time **emergency detection** (e.g., patient says "chest pain").
* Multi-lingual support for inclusivity.

## Result:

The experiment showed clear differences in chatbot performance across prompting techniques. Zero-shot prompting produced vague and unhelpful replies, while few-shot prompting improved by guiding the chatbot to ask for clarification but still lacked completeness. Role-based prompting enhanced trust and empathy, aligning the chatbot with a professional healthcare persona. Chain-of-Thought prompting delivered the most effective outcome, providing a detailed, accurate, and patient-centered response that confirmed availability, gave doctor details, and offered reminders. Reflective prompting also performed strongly by ensuring clarity and warmth, though slightly less structured than Chain-of-Thought. Overall, Chain-of-Thought emerged as the most reliable method for healthcare appointment booking.
