# SOCShield – Day 1 Detection Scenarios

## Scenario A: Repeated Failed Logins

Purpose:
Identify possible password guessing or brute-force activity.

Event/Data Needed:
Failed authentication events, source IP, username and timestamp.

Example Condition:
5 or more failed login events from the same source IP
within 5 minutes.

Analyst Investigation:
1. Identify source IP.
2. Identify targeted usernames.
3. Check timestamps.
4. Check whether a successful login followed.
5. Verify whether the activity is expected.

Limitations:
Legitimate users may enter incorrect passwords.
Thresholds must be tuned to the environment.

## Scenario B: One Host Contacts Many Ports

Purpose:
Identify possible port-scanning behavior.

Event/Data Needed:
Source IP, destination IP, destination ports,
connection timestamps and connection outcomes.

Example Condition:
One source IP contacts 20 or more distinct destination
ports on the same host within 1 minute.

Analyst Investigation:
1. Identify source IP.
2. Identify destination IP.
3. Review destination ports.
4. Check connection outcomes.
5. Verify whether the source is an approved scanner.

Limitations:
Authorized network scanning and asset discovery
may produce similar activity.

## Scenario C: Unusual Outbound Connections

Purpose:
Identify outbound connections that differ from
the organization's normal baseline or policy.

Event/Data Needed:
Source device, destination IP/domain, destination port
and connection information.

Example Condition:
Alert when an outbound destination, port or connection
pattern violates a documented allowlist or baseline.

Analyst Investigation:
1. Identify the source device.
2. Identify the destination.
3. Check the destination port.
4. Review frequency of connections.
5. Check process and user context if available.
6. Verify the business purpose.

Limitations:
Unfamiliar connections are not automatically malicious.
A local baseline or policy is required.
