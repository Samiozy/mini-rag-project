# Cybersecurity Study Notes: Detection And Incident Response

# Intrusion Detection and Prevention
An intrusion detection system (IDS) monitors network or host activity and raises alerts on suspicious behavior, while an intrusion prevention system (IPS) goes further and actively blocks malicious traffic. Signature-based detection matches activity against a database of known attack patterns, whereas anomaly-based detection flags deviations from a learned baseline of normal behavior. Anomaly detection can catch previously unseen attacks but tends to generate more false positives that analysts must triage.

# Security Operations Center
A Security Operations Center (SOC) is the team and facility responsible for continuous monitoring and defense of an organization. Analysts rely on a Security Information and Event Management (SIEM) platform to aggregate logs from across the enterprise, correlate related events, and surface prioritized alerts. SOC effectiveness is commonly measured by the mean time to detect (MTTD) and the mean time to respond (MTTR) to security incidents.

# Incident Response
Incident response is the structured process organizations follow when a security breach occurs. The widely adopted NIST framework defines four phases: preparation; detection and analysis; containment, eradication, and recovery; and post-incident activity. Containment isolates affected systems to stop the threat from spreading, eradication removes the malicious presence, and recovery restores normal operations. A post-incident review then captures lessons learned so future responses improve.

## Additional study notes (AI-assisted draft; review before submission)
Detection and prevention systems have different operational effects. An IDS primarily observes and raises alerts, whereas an IPS can interrupt traffic under its blocking policy. Signature-based rules are useful for recognizable patterns; anomaly-based approaches may surface previously unseen behavior but require careful tuning to manage false positives. Analysts correlate events rather than assume every isolated alert is a confirmed incident.

A SOC uses logs and alerts to assess whether a threat requires escalation. MTTD summarizes elapsed time before detection, while MTTR summarizes elapsed time to respond; exact metric definitions should be kept consistent when results are compared. Incident response organizes decisions into preparation, investigation, containment, eradication, recovery, and learning activities. Containment may trade some service availability for reduced harm. A post-incident review should document what was observed, which decisions worked, and how preventive controls or procedures could improve.
