# Freight Invoice Reconciliation, Gap Analysis and RPA Automation

**Portfolio Project, N M Ziyaf**
Supply Chain Business Analyst

---

## Overview

I was asked to examine the freight invoice reconciliation process operating inside a CargoWise One freight forwarding environment, because finance and operations suspected that carrier overcharges were passing through unchallenged. This repository contains the gap analysis BRD I produced from that review, the RPA business case I developed as the recommended solution, and the current state and future state process maps that support both documents.

---

## The Real Problem

The team believed it was reconciling invoices, but in practice it was performing a total level sanity check. Carrier invoices were compared against freight quotes at the invoice total level only, with no systematic three way match against the underlying shipment record. Spot check sampling found that only around 15 percent of invoices received a full three way comparison, and roughly 6 percent carried a rate variance that no one had detected.

This is a financial control gap, not a speed problem. An overcharge on one charge code can be offset by an undercharge on another so the total still reconciles, while the actual variance passes through undetected.

---

## Why I Rejected the Simple Automation Approach

The obvious automation is a bot that reads each invoice, captures the total, and auto approves anything close to the quoted figure. I considered this and rejected it deliberately. Automating the existing total level check would simply apply the same flawed logic faster, and would likely reduce the human scrutiny that currently catches some of these cases by chance. Faster processing with weaker control is the opposite of what the gap analysis called for.

The solution I propose instead matches every invoice at the individual charge code line level against both the freight quote and the shipment record, applies a configurable variance tolerance, and escalates only genuine discrepancies to a human approver. Automation strengthens the control rather than just accelerating the existing one.

---

## Key Findings

| Gap Area | As-Is State | To-Be State | Priority |
|----------|-------------|-------------|----------|
| Three way matching | Invoice total compared to quote only, no shipment cross check | Each charge code line matched against quote and shipment record | High |
| Variance tolerance and escalation | Subjective decision on when totals differ enough to query | Configurable tolerance threshold with automatic escalation | High |
| Invoice data extraction consistency | PDF and Excel read and re-keyed by hand | Invoice data extracted and normalised into a common structure | Medium |

---

## Target Outcomes

| Metric | Baseline | Three Month Target |
|--------|----------|---------------------|
| Invoices receiving a full three way match | 15 percent | 100 percent |
| Undetected rate variance | 6 percent of invoices | Below 1 percent |
| Average processing time per invoice | 22 minutes | Under 6 minutes |
| Approval cycle time | 3.1 days | Under 1 day |

---

## Financial Case

| Measure | Value |
|---------|-------|
| Year 1 total investment | AUD 26,200 |
| Year 1 gross benefit | AUD 72,000 |
| Net Year 1 benefit | AUD 45,800 |
| First year return on investment | Approximately 175 percent |
| Payback period | Approximately 6 months |

---

## Files in This Repository

**BRD_Freight_Invoice_Reconciliation.docx** and **.pdf**
The full gap analysis BRD. Covers organisational context, problem statement, business impact, scope, stakeholders, as-is process analysis with 5-Why root cause analysis, gap analysis, nine functional requirements traced to three gap areas, to-be process design, non-functional requirements, UAT approach with five test scenarios, implementation plan, success metrics, assumptions and constraints, and document control.

**RPA_Business_Case_Freight_Invoice.docx** and **.pdf**
The RPA business case that follows from the BRD. Covers the executive summary, the rationale for rejecting simple total level automation in favour of three way matching, full cost benefit analysis with implementation costs and projected benefits in Australian dollars, risk assessment, a five phase implementation approach including a mandatory parallel run, recommendation, and document control.

**asis_bpmn.png**
Current state process map showing the manual reconciliation workflow across the Accounts Payable Team and CargoWise One, with the total level comparison flaw and the subjective approval judgement flaw annotated directly on the diagram.

**tobe_bpmn.png**
Future state process map showing the proposed RPA bot workflow across the RPA Bot, CargoWise One, and Accounts Payable Team lanes, with the three way matching step and the escalation logic for genuine variance shown in detail.

---

## Methodology Applied

Gap analysis using as-is and to-be state mapping. Root cause analysis using the 5-Why methodology applied in full prose to two material problems. Requirements elicitation producing nine functional requirements with direct traceability to the three identified gaps. UAT design with five test scenarios covering clean invoices, tolerance breaches, offsetting line errors, unsupported charges, and unfamiliar invoice formats. Cost benefit analysis and return on investment calculation. Risk assessment focused on the three risks that specifically bear on this solution rather than generic project risk. Process mapping in BPMN swimlane format for both current and future state.

---

## Author

N M Ziyaf

Supply Chain Business Analyst, Sydney NSW

linkedin.com/in/ziyafmohamed
