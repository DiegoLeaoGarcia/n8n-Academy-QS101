# Customer Service Agent

> **Navigation:** [Course portfolio](../../) › [Module 03](../) › Customer Service Agent

An n8n conversational agent that combines an OpenRouter-hosted language model, short-term memory, a customer Data Table, and an authenticated order API.

![Customer Service Agent architecture](../assets/customer-service-agent.svg)

## Architecture

| Component | Node | Responsibility |
| --- | --- | --- |
| Interface | `When chat message received` | Receive user messages and display responses |
| Orchestration | `AI Agent` | Interpret the request, select tools, and compose the answer |
| Reasoning | `OpenRouter Chat Model` | Provide the language model used by the agent |
| Context | `Simple Memory` | Append recent interactions to the model context |
| Customer tool | `GetCustomers` | Retrieve customer, country, email, region, and subregion data |
| Order tool | `GetOrderData` | Retrieve order, employee, price, quantity, category, and status data |

## System behavior

- Use `GetCustomers` for customer information.
- Use `GetOrderData` for orders, prices, employees, and product categories.
- Keep responses concise and helpful.
- State when requested information is unavailable.
- Never invent information missing from tool results.

## Verified scenarios

| Question | Expected capability |
| --- | --- |
| “What country is customer 7 from?” | Customer tool lookup |
| “Who is assigned to order 5?” | Order tool lookup |
| “What region is the customer who placed order 24 in?” | Multi-tool reasoning |
| “What’s my name?” after an introduction | Conversation memory |

## Import

1. Download [`workflow.json`](./workflow.json).
2. Import it into n8n.
3. Reconnect your authorized credentials.
4. Select your local customer Data Table.
5. Replace `YOUR_ASSESSMENT_ID` only inside your private n8n instance.
6. Review the selected model’s tool-calling support before testing.

The public workflow is intentionally inactive and contains no credential objects or instance-specific identifiers.

---

[Back to Module 03](../)
