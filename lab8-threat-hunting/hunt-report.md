# Threat Hunting Investigation Report

## Investigation Information

- **Lab:** Lab 08 – Threat Hunting Fundamentals
- **Investigator:** Samuel Iyiola Taiwo
- **Date:** <Date>
- **Platform:** Splunk Enterprise
- **Data Source:** Splunk Internal Logs (`_internal`)

---

# Investigation Objective

The objective of this investigation was to proactively search Splunk internal logs for unusual or suspicious activity using a hypothesis-driven threat hunting approach.

---

# Hunting Hypothesis

If a service is repeatedly failing, there should be an increased number of ERROR events recorded within Splunk's internal logs.

---

# Data Source

The investigation used the following data source:

- Splunk Internal Logs (`index=_internal`)

---

# Investigation Steps

## Step 1 – Explore Available Events

Search used:

```spl
index=_internal
```

Purpose:

- Identify available events
- Observe hosts
- Observe sourcetypes
- Understand the available data

---

## Step 2 – Search for Error Events

Search used:

```spl
index=_internal log_level=ERROR
```

Purpose:

- Identify internal system errors
- Determine which components generated errors

---

## Step 3 – Search for Warning Events

Search used:

```spl
index=_internal log_level=WARN
```

Purpose:

- Compare warning events with error events
- Identify recurring warnings

---

## Step 4 – Analyze Hosts

Search used:

```spl
index=_internal
| stats count by host
```

Purpose:

Determine which hosts generated the highest number of events.

---

## Step 5 – Analyze Event Sources

Search used:

```spl
index=_internal
| stats count by source
```

Purpose:

Identify which Splunk components generated the largest amount of log data.

---

## Step 6 – Analyze Activity Over Time

Search used:

```spl
index=_internal
| timechart count
```

Purpose:

Identify spikes or unusual increases in log activity.

---

# Findings

During the investigation:

- Internal Splunk logs were successfully analyzed.
- Error events were identified.
- Warning events were identified.
- Event frequency was visualized using a timechart.
- Host and source statistics were generated.
- No clear evidence of malicious activity was observed within the available dataset.

---

# Conclusion

The hunting hypothesis could not be confirmed using the available internal log data.

Although error events were present, they appeared to be related to normal Splunk operations rather than malicious activity.

This investigation demonstrated the importance of validating assumptions with evidence rather than relying on intuition.

---

# Recommendations

Future investigations should include:

- Windows Event Logs
- Sysmon logs
- Authentication logs
- DNS logs
- Firewall logs
- Endpoint Detection and Response (EDR) telemetry

These additional data sources would improve visibility and increase the likelihood of identifying malicious activity.

---

# Skills Demonstrated

- Threat Hunting
- Log Analysis
- Splunk SPL
- Evidence-Based Investigation
- Hypothesis Development
- Security Documentation
- Analytical Thinking

---

# MITRE ATT&CK Mapping

No specific adversary techniques were identified during this investigation because the available dataset contained only Splunk internal operational logs.

---

# Lessons Learned

This investigation reinforced that threat hunting is a proactive process that begins with a hypothesis and relies on evidence gathered from logs. Even when no malicious activity is discovered, documenting the investigation provides valuable insight into normal system behavior and strengthens future detection efforts.

