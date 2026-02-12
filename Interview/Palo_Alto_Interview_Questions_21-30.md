
# Palo Alto Interview Questions (21–30) with Detailed Answers

Below are questions **21 to 30** with clear, practical explanations.

---

## **21. Explain the difference between GlobalProtect internal gateway and external gateway.**

### **Answer:**
- **External Gateway:** Used by users connecting from the internet. Provides VPN tunneling, HIP checks, and authentication.
- **Internal Gateway:** Used inside the corporate network to enforce user authentication and HIP checks **without tunneling**.

---

## **22. Describe the steps to configure an IPSec VPN tunnel in Palo Alto.**

### **Answer:**
1. Create **IKE Crypto Profile**.
2. Create **IKE Gateway** (peer IP, PSK, interface).
3. Create **IPSec Crypto Profile**.
4. Create a **Tunnel Interface**.
5. Create the **IPSec Tunnel** object.
6. Configure **Proxy IDs** (if policy‑based).
7. Add **static routes**.
8. Add **Security Policies**.

---

## **23. What is IKEv2, and why is it preferred over IKEv1?**

### **Answer:**
- Faster and more efficient negotiation.
- Supports mobility (MOBIKE).
- Stronger encryption.
- Fewer message exchanges.
- More stable with NAT‑Traversal.

---

## **24. How do you troubleshoot a VPN tunnel that is not coming up?**

### **Answer:**
- Check Phase‑1 SAs: `show vpn ike-sa`
- Check Phase‑2 SAs: `show vpn ipsec-sa`
- Verify pre‑shared key.
- Match crypto profiles.
- Validate Proxy IDs.
- Check NAT‑T.
- Review logs (System / IPSec).

---

## **25. What are tunnel monitoring and dead peer detection (DPD)?**

### **Answer:**
- **Tunnel Monitoring:** Firewall pings a remote IP across the tunnel; triggers failover if unreachable.
- **DPD:** Detects unresponsive peers and renegotiates SAs.

---

## **26. What are the primary tools for troubleshooting on a Palo Alto firewall?**

### **Answer:**
- `test security-policy-match`
- `test nat-policy-match`
- `show session all filter ...`
- Packet captures
- Global counters
- Traffic/Threat/System logs

---

## **27. How do you use the packet capture feature?**

### **Answer:**
1. Create filters.
2. Select capture stages (receive, drop, transmit).
3. Enable capture.
4. Reproduce issue.
5. Download PCAP.

---

## **28. What is the purpose of the show session all filter command?**

### **Answer:**
Used to:
- Check active sessions
- Verify NAT translations
- Confirm traffic reaching firewall
- Inspect session state, timeout, app

---

## **29. Explain the different logging types (Traffic, Threat, System, etc.).**

### **Answer:**
- **Traffic:** Allow/deny session logs
- **Threat:** IPS/AV/Spyware/WildFire
- **URL Filtering:** Website category logs
- **System:** HA events, process failures
- **Config:** Commit history
- **HIP:** GlobalProtect posture logs

---

## **30. A user reports slow internet — walk through your troubleshooting steps.**

### **Answer:**
1. Check session logs.
2. Inspect Threat/URL logs.
3. Check interface counters.
4. Verify routing + NAT.
5. Test without decryption or profiles.
6. Run pings/traceroute.
7. Capture packets.
8. Review QoS policies.

---

