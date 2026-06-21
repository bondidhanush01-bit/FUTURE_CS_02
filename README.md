# Corporate Phishing Detection & Threat Analysis Lab

## Objective
This repository demonstrates a production-ready approach to corporate security awareness, indicator-of-compromise (IoC) isolation, and email perimeter protection frameworks.

## Tools Utilized
* **Google Admin Toolbox (Messageheader):** Utilized for processing cryptographic verification checks (SPF/DKIM/DMARC) and validating hop-latency time deltas within email headers.
* **MXToolbox Email Header Analyzer:** Employed for checking sender IP reputation against real-time global blacklists (DNSBL).
* **Sanitized Browser Isolation Environment:** Used to safely analyze and document target destination URLs without risking host compromise.

## Analysis Approach
1. **Header Analysis:** Extract and audit routing hops and cryptographic signatures to identify spoofing attempts.
2. **Body Inspection:** Parse contextual indicators, lexical anomalies, and targeted social engineering vectors.
3. **Risk Classification:** Map observed threat indicators against the corporate Threat Classification Matrix to determine containment steps.
4. **Documentation:** Synthesize findings into standard, executive-ready remediation and awareness material.
