#  Social Engineering & MFA Recovery

## 🎫 The Ticket

It's 26 October 2026, my fourth week on the security team at Northwind Health. The Help Desk has escalated an MFA reset request after an agent became concerned about the caller.

<br>

The IT Manager writes:

> The help desk escalated a call to us. Someone says she's Dana Whitfield, our VP of Finance, locked out while travelling, and wants her MFA reset to a new phone. The agent sounded uneasy, but she gave him everything he asked for. What should have happened, and how do we fix our process?

<br>


**Supporting Information:** [Help Desk Call Notes](document/01.Source%20Data.md)

<br>


<table>
<tr>
<td>

**🛡️ Decision**

**Do not reset MFA until the caller's identity has been independently verified.**

The caller refused further verification, asked the agent not to call back and provided information that conflicted with company records.

Because the account can approve payments and access the bank portal, I recommended pausing the reset and following the approved verification process.

The warning signs raised concerns but did not confirm impersonation.

</td>
</tr>
</table>

<br>

## What's the Risk?

Dana's account can approve payments and access the bank portal. An unauthorised MFA reset could give an attacker control of both.

The Help Desk has already spotted warning signs. The caller knows personal details about Dana, but some of the information doesn't match what the organisation has on record.

<br>

## The Investigation

At first, this looked like an urgent MFA recovery request. But the caller's behaviour and conflicting information made me question whether it was genuine. I looked into how an attacker might manipulate the help desk's recovery process.

Five questions guided my investigation:

1. What warning signs should have concerned the help desk agent?
2. What should the agent do during the call, and what should they say to the caller?
3. Which identity verification methods are strong or weak, and why?
4. How should MFA recovery work for privileged accounts?
5. If this was an impersonation attempt, what should happen after the call?

<br>

## What I Found

Three details immediately concerned me.

| Area | Finding |
|---|---|
| **Identity verification** | The caller knew personal details but declined further verification and asked the agent not to call back. |
| **Conflicting information** | The UK calling number didn't match HR records, and Dana's Austin meetings raised questions about her travel story. |
| **Privileged access** | An unauthorised MFA reset could expose payment approvals and the bank portal. |

None of these details proves the caller was an impersonator. But together, they make the request too risky to approve without stronger verification.

<br>

## Decisions & Recommendations

**Do first: no independent identity verification, no MFA reset.**

My experience in billing and payment support taught me that verification comes before discussing or changing account information. If a customer couldn't be verified, I couldn't proceed, however urgent the request sounded. I would apply the same rule here. The agent should pause the reset, explain that additional checks are required and use an independently verified method rather than the details given during the call.

**Improve the process**

- Add an escalation button to the Help Desk ticketing system for suspicious identity and MFA recovery requests. It could capture the ticket details, record the warning signs and route the case to Security or IAM.
- If the organisation adopts AI agents, this structured information could help them identify recurring patterns, highlight missing evidence and support investigations. Human oversight should remain essential, especially for privileged account recovery.

<br>

## Looking Back at the Review

Social engineering fascinates me because it targets something more complicated than technology: **human judgement**. It is the art of manipulation, using emotions, trust, authority and urgency to influence decisions.

In this case, the caller wasn't trying to break MFA. They were trying to influence the person with the power to reset it, making an exception seem reasonable.

This reinforced two lessons for me:

- **IAM goes beyond granting or restoring access.** It also means recognising suspicious behaviour, examining the evidence and making decisions that protect both the account and the business.
- **How we communicate a security boundary matters as much as the boundary itself.** Until someone's identity is verified, we cannot assume they are who they say they are, but that doesn't mean treating them with suspicion or making them feel judged. We can acknowledge their situation, explain the next steps and remain firm about verification.

Understanding the attacker's mindset helps me recognise manipulation. A defender's responsibility is to protect access without losing professionalism.

<br>

## What I Will Improve Next Time

I want to deepen my understanding of security governance and recognised frameworks, so my risk assessments and recommendations are not based on judgement alone.

My goal is to make decisions that are supported by evidence, aligned with organisational policies and easier to explain, justify and audit.


<br>



## Explore the Investigation

| Document | Focus |
|:---------|:------|
| [01. Source Data](document/01.Source%20Data.md) | Original call notes and account context. |
| [02. Red Flags & Risk Assessment](document/02.%20Red%20Flags%20%26%20Risk%20Assessment.md) | Warning signs and potential impact. |
| [03. Help Desk Call Handling](document/03.%20Help%20Desk%20Call%20Handling.md) | Call flow, verification checks and what to say to the caller. |
| [04. Identity Verification Methods](document/04.%20Identity%20Verification%20Methods.md) | Strong and weak verification methods. |
| [05. Privileged Account Recovery](document/05.%20Privileged%20Account%20Recovery.md) | 5 step recovery process and additional safeguards. |
| [06. Digging Deeper](document/06.%20Digging%20Deeper.md) | Follow up actions if the call was an impersonation attempt. |

<br>

---



[← Week 3: AI Agent Security Review](https://github.com/itsanitarose/IAM-AI-Agent-Security-Review) · [All Case Studies](https://github.com/itsanitarose/IAM-Case-Studies) · [Week 5: SAML SSO Troubleshooting →](https://github.com/itsanitarose/IAM-SAML-SSO-Troubleshooting)

*<sub>Northwind Health is fictional. This is independent work. No production systems were changed.</sub>*
