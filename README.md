# Requirement Analysis in Software Development

Welcome! This repo is a mini guide + example artifacts for understanding **Requirement Analysis** using a simple **Booking Management System** (think hotel/room booking).

---

## What is Requirement Analysis?

- Requirement Analysis is the process of **discovering, understanding, documenting, and validating** what a software system must do.
- It happens early in the **Software Development Life Cycle (SDLC)** and guides design, development, testing, and deployment.
- Goals:
  - Capture **what users/business need** (not just what features sound cool).
  - Make requirements **clear, consistent, and testable**.
  - Reduce rework and surprises later in the project.

---

## Why is Requirement Analysis Important?

1. **Reduces costly rework**
   - Fixing unclear requirements late (during dev/test) is far more expensive than clarifying early.
2. **Aligns stakeholders**
   - Creates a shared understanding between business, users, and the dev team.
3. **Enables better design & testing**
   - Clear requirements -> better architecture choices and **test cases** that trace back to requirements.
4. **Improves predictability**
   - Better estimates, prioritization, and risk management.

---

## Key Activities in Requirement Analysis

- **Requirement Gathering**
  - Identify stakeholders (customers, support, finance, etc.).
  - Collect needs via interviews, surveys, observation, and existing docs.
- **Requirement Elicitation**
  - Ask the right questions; use workshops, brainstorming, and prototypes.
  - Resolve conflicts between stakeholder needs.
- **Requirement Documentation**
  - Write clear **User Stories**, **Use Cases**, and **SRS** (Software Requirements Specification).
  - Use simple, unambiguous language with acceptance criteria.
- **Requirement Analysis and Modeling**
  - Organize & model with **Use Case Diagrams**, **User Flows**, and **Data Models**.
  - Check for completeness, consistency, feasibility, and priority.
- **Requirement Validation**
  - Walkthroughs, reviews, and demonstrations with stakeholders.
  - Trace requirements to test cases (RTM: Requirements Traceability Matrix).

---

## Types of Requirements

### Functional Requirements (what the system must do)
Examples for the booking system:
- Users can **search listings** by date, location, price, and capacity.
- Users can **view availability** for selected dates.
- Users can **register, log in, and recover password** via email OTP.
- Users can **make a booking** and receive an **email/SMS confirmation**.
- Users can **modify or cancel** a booking before check-in.
- System **calculates total cost**, taxes/fees, and **applies promo codes**.
- System processes **secure payments** and **handles refunds** for cancellations.
- Admin can **add/edit/remove listings** and **view bookings** and reports.

### Non-functional Requirements (how well the system works)
Examples for the same system:
- **Performance:** Search results return in **≤ 2 seconds** for 95% of requests.
- **Availability:** System uptime **≥ 99.5%** monthly.
- **Security:** All traffic over **HTTPS**; payments via **PCI-DSS compliant** gateway.
- **Scalability:** Support **500 concurrent users** without performance degradation.
- **Usability:** New users can complete a booking in **≤ 3 minutes** without help.
- **Reliability:** No more than **1 failed payment in 10,000** due to system errors.
- **Maintainability:** Codebase has **≥ 80% unit test coverage** and clear docs.
- **Compliance:** Store personal data per **POPIA/GDPR** principles.

---

## Use Case Diagrams

- A **Use Case Diagram** shows **actors** (people/systems) and the **goals** (use cases) they want from the system.
- Benefits:
  - Gives a **high-level view** everyone can understand.
  - Helps spot **missing functionality** and **actor responsibilities**.
  - Supports scope discussions and prioritization.

**Booking System – Use Case Diagram**  
![Use Case Diagram](alx-booking-uc.png)

Actors: **Customer**, **Admin**, **Payment Gateway**  
Key Use Cases: Search Listings, View Availability, Create Account/Login, Make Booking, Modify/Cancel Booking, Checkout/Payment, Receive Confirmation, Manage Listings, Refunds, Generate Reports.

---

## Acceptance Criteria

- Acceptance Criteria make a requirement **testable** and set the **conditions of satisfaction**.
- They keep everyone aligned on **what “done” means**.

**Example – Checkout feature** (as User Story):  
> As a customer, I want to pay for my booking so that my reservation is confirmed.

**Acceptance Criteria (Given/When/Then):**
- **Given** I have selected dates and a listing, **when** I open checkout, **then** I see a summary with price, taxes/fees, and total.
- **Given** I enter valid card details, **when** I submit payment, **then** the system processes payment via the payment gateway and marks the booking as **Paid**.
- **Given** payment succeeds, **when** it completes, **then** I receive an **email/SMS confirmation** with booking details and a unique reference number.
- **Given** payment fails (gateway declines or network error), **when** I submit, **then** I see a clear error, my booking remains **Unpaid**, and I can retry or use another method.
- **Given** I cancel within the refundable window, **when** I request a refund, **then** the system issues a refund through the gateway and emails a refund receipt.

---

## Repo Setup

- Repo name: **requirement-analysis**
- Main file: **README.md** (this document)
- Asset: **alx-booking-uc.png** (Use Case Diagram)
