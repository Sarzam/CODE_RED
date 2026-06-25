# AI-kNOC

**Team:** Code Red: Karthik Ravishankar, Misbah Shaikh, Najid Navas

AI-kNOC is an AI-powered Network Operations Command Center that turns fragmented operational signals into one real-time incident intelligence view.

During an outage, engineers usually jump between router telemetry, VM health, application dashboards, support tickets, change logs, and business impact reports. AI-kNOC uses Confluent Cloud as the streaming foundation to bring these signals together, Flink SQL to correlate them in real time, and AI to explain root cause, impact, and recommended actions.

## The Problem

Modern incidents rarely live in one tool.

A network issue may first appear as interface telemetry, then show up as application latency, failed transactions, customer complaints, and support escalations. Teams lose time manually connecting these signals across different systems.

AI-kNOC solves this by creating a live incident command layer over streaming data.

## What AI-kNOC Does

AI-kNOC continuously ingests and correlates:

- IOS XR network telemetry
- VM/server health metrics
- application latency and error signals
- business impact events such as failed orders and revenue at risk
- support complaint signals
- change/deployment context

It then produces:

- live network and service health
- correlated incident candidates
- severity scoring
- business impact context
- AI-generated RCA
- recommended remediation actions
- stakeholder-ready incident updates

## Confluent-Powered Flow

```text
Network telemetry
+ VM health
+ app health
+ business impact
+ support signals
+ change events
  -> Confluent Cloud
  -> Schema Registry
  -> Flink SQL windowing, joins, scoring, and anomaly detection
  -> AI RCA
  -> AI-kNOC dashboard
```

## Why It Stands Out

AI-kNOC is not a generic chatbot over logs. It is a real-time incident commander powered by streaming data.

The system demonstrates:

- multiple live operational streams
- Confluent Cloud topics as the real-time data backbone
- Schema Registry for governed event contracts
- Flink SQL for windowed stream correlation and scoring
- Stream Lineage from source signals to incident outputs
- AI RCA grounded in real-time evidence
- a practical NOC/SRE use case with clear business impact

## Flink Usage

Flink is the real-time reasoning layer in AI-kNOC.

It is used for:

- one-minute tumbling windows
- multi-source joins by site and time window
- network, VM, app, business, support, and change-event scoring
- incident severity calculation
- anomaly detection with Flink AI/ML functions where available
- AI-ready incident evidence generation

## AI RCA

AI-kNOC uses AI to transform correlated stream evidence into actionable incident guidance:

- likely root cause
- supporting evidence
- recommended remediation
- business impact
- stakeholder update

The AI layer is designed to explain *why* an incident is happening, not just that a metric crossed a threshold.

## Demo Scenario

The demo shows a realistic incident flow:

1. Network telemetry and VM health stream into Confluent.
2. Application and business signals begin showing degraded user experience.
3. Support complaints and change context provide additional evidence.
4. Flink correlates the streams and computes incident severity.
5. AI-kNOC generates a root-cause explanation and recommended actions.
6. Stream Lineage shows the real-time path from source signals to incident intelligence.

## Security And Data Handling

AI-kNOC is designed with safe demo and enterprise practices:

- internal identifiers are sanitized before leaving the source environment
- no credentials are exposed in the browser
- internal systems are not exposed publicly
- public/demo views use sanitized telemetry and generated business/support signals

## Team

**Code Red**
