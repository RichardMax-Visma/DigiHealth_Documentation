# NHN Documentation

Mermaid diagrams and documentation for Norsk Helsenett (NHN) APIs.

## APIs

### HelsenorgeAktivSjekken
Check if citizens are digitally active on Helsenorge.

📁 [Documentation](./diagrams/HelsenorgeAktivSjekken/HelsenorgeAktivSjekken_README.md)

| Diagram | Description |
|---------|-------------|
| [Flow](./diagrams/HelsenorgeAktivSjekken/HelsenorgeAktivSjekken_Flow.mmd) | REST API sequence |
| [Classes](./diagrams/HelsenorgeAktivSjekken/HelsenorgeAktivSjekken_Classes.mmd) | Request/Response models |

---

### Helsekontakt
Citizen's entry point for digital healthcare communication.

📁 [Documentation](./diagrams/Helsekontakt/README.md)

| Sub-API | Technology | Documentation |
|---------|------------|---------------|
| AMQP Tjenesteoversikt | AMQP | [Docs](./diagrams/Helsekontakt/AMQP%20Tjenesteoversikt/AMQP_Tjenesteoversikt_README.md) |
| Medlemstjenester | FHIR | [Docs](./diagrams/Helsekontakt/Medlemstjenester/Medlemstjenester_README.md) |
| AMQP Notifikasjon | AMQP + FHIR | [Docs](./diagrams/Helsekontakt/AMQP%20Notifikasjon%20Helsekontakt/AMQP_Notifikasjon_README.md) |

---

## Quick Reference

| API | Tech | Purpose |
|-----|------|---------|
| HelsenorgeAktivSjekken | REST | Check if citizen is digitally active |
| AMQP Tjenesteoversikt | AMQP | Home care health contacts |
| Medlemstjenester | FHIR | Membership-based health services |
| AMQP Notifikasjon | AMQP+FHIR | General health contact notifications |

## Viewing Diagrams

The `.mmd` files are Mermaid diagrams. You can view them:
- **VS Code**: Install "Mermaid Preview" extension
- **GitHub**: Renders automatically in preview
- **Online**: Paste into [Mermaid Live Editor](https://mermaid.live)
