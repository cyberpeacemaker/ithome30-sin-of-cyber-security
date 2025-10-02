A **supply-chain attack** is a type of cyberattack that targets less-secure elements in an organization's supply chain — such as third-party vendors, software providers, or service contractors — to gain access to the primary target.

### In simple terms:

Instead of attacking a company directly, attackers infiltrate it by compromising trusted partners or software that the company uses.

---

### Key Concepts

| Term              | Meaning                                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| **Supply Chain**  | The network of external partners (software, hardware, services, etc.) that help an organization operate. |
| **Attack Vector** | The weak point in a supplier or vendor the attacker exploits.                                            |
| **Target**        | The ultimate organization or individual the attacker wants to harm or access.                            |

---

### How It Works (Example)

1. **Company A** uses software from **Vendor B**.
2. An attacker compromises **Vendor B’s** software (e.g. by injecting malicious code).
3. When **Company A** installs or updates the software, they unknowingly install the malicious code.
4. The attacker now has access to **Company A’s** systems.

---

### Real-World Examples

* **SolarWinds (2020)**: Attackers inserted malware into updates of the SolarWinds Orion software, affecting thousands of organizations, including U.S. government agencies.
* **NotPetya (2017)**: Russian attackers compromised a Ukrainian accounting software update to spread malware globally.

---

### Why It’s Dangerous

* **Hard to Detect**: The attack comes from a trusted source.
* **Widespread Impact**: One compromised vendor can affect many organizations.
* **Trust Exploitation**: It undermines the chain of trust in software and services.

---

### Prevention Tips

* Vet third-party vendors thoroughly.
* Use **Software Bill of Materials (SBOM)** to know what's in your software.
* Monitor software updates and network behavior.
* Implement zero-trust security practices.

---

Let me know if you'd like a visual or analogy to understand it better.
