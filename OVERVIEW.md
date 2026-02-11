# 📚 Project Overview: The Coolykos Architecture

> A real-world case study of an ideal AI workspace structure for a Kost Management SaaS platform.

---

## 🏢 What is Coolykos?

**Coolykos** is a comprehensive Kost Management SaaS platform designed for property owners and tenants in Indonesia. It represents the ideal structure for a vibe-coded project with multiple user roles, complex workflows, and scalable architecture.

### User Roles

| Role | Description | Access Level |
| :--- | :--- | :--- |
| **Penghuni** (Tenant) | End-users who rent rooms | Mobile App + Web Dashboard |
| **Admin** | Property managers who handle operations | Web Dashboard (Full) |
| **Owner Property** | Property owners with full control | Web Dashboard (Super Admin) |

---

## 🏗️ Architecture Overview

### Monorepo Structure

```
coolykos/
├── apps/
│   ├── web-tenant/           # Next.js 15 - Tenant-facing web
│   ├── web-dashboard/        # Next.js 15 - Admin & Owner dashboard
│   └── mobile/               # Expo + React Native - Tenant mobile app
│
├── packages/
│   ├── database/             # Drizzle schema + migrations (shared)
│   ├── api/                  # Hono RPC routes (shared types)
│   └── ui/                   # shadcn/ui components (shared)
│
└── .agent/                   # Control Plane
    ├── AGENT.md              # CEO Router (already at root)
    ├── SKILL.md              # Tech stack definition (already at root)
    ├── PROJECT_STATUS.md     # Memory file (already at root)
    │
    ├── sop/                  # Standard Operating Procedures
    │   ├── UI_WORKFLOW.md    # Frontend development rules
    │   ├── BACKEND_WORKFLOW.md  # API & database rules
    │   ├── DEBUG_WORKFLOW.md    # Bug fixing protocol
    │   ├── BILLING_WORKFLOW.md  # Midtrans integration rules
    │   └── IOT_WORKFLOW.md      # Smart lock & device management
    │
    └── memory/               # Immutable facts & decisions
        ├── DECISION_LOG.md   # Why we chose this stack
        ├── API_CONTRACTS.md  # API documentation
        └── MIGRATION_LOG.md  # Database migration history
```

---

## 🎯 Key Features

### For Tenants (Penghuni)
- **Room Booking**: Browse and book available kost rooms
- **Payment Management**: Pay rent via Midtrans integration
- **Maintenance Requests**: Submit and track repair tickets
- **Smart Access**: Unlock doors via IoT smart locks
- **Community Chat**: Connect with other tenants

### For Admins
- **Tenant Management**: Onboard and manage tenant accounts
- **Payment Tracking**: Monitor rent payments and send reminders
- **Room Management**: Update room availability and pricing
- **Maintenance Dashboard**: Track and assign repair tasks
- **Reports**: Generate occupancy and financial reports

### For Property Owners
- **Multi-Property Dashboard**: Manage multiple kost locations
- **Financial Analytics**: Revenue tracking and expense management
- **Admin Management**: Assign and manage admin roles
- **Business Intelligence**: Occupancy rates and market insights
- **Wholesale Operations**: Manage supply chain for kost amenities

---

## 🛠️ Technology Stack

### Frontend
| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Framework** | Next.js 15 (App Router) | Server-first React |
| **Styling** | Tailwind CSS v4 | Utility-first CSS |
| **UI Components** | shadcn/ui | Accessible primitives |
| **State** | Zustand + TanStack Query | Global + Server state |
| **Forms** | react-hook-form + Zod | Type-safe forms |

### Backend
| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **API Framework** | Hono (RPC) | Type-safe API routes |
| **Database** | PostgreSQL | Relational data |
| **ORM** | Drizzle ORM | Type-safe SQL |
| **Auth** | Better Auth | Session-based auth |
| **Payments** | Midtrans | Indonesian payment gateway |

### Mobile
| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Framework** | Expo + React Native | Cross-platform mobile |
| **Navigation** | Expo Router | File-based routing |
| **State** | Zustand | Global state |
| **API** | tRPC Client | Type-safe API calls |

### DevOps & Infrastructure
| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Containerization** | Docker | Consistent environments |
| **Orchestration** | Docker Compose | Local development |
| **Hosting** | Coolify / VPS | Self-hosted deployment |
| **CI/CD** | GitHub Actions | Automated testing & deploy |
| **Monitoring** | Sentry | Error tracking |

### IoT (Smart Locks)
| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Firmware** | ESP32 + Arduino | Smart lock hardware |
| **Protocol** | MQTT | Device communication |
| **Backend** | Node.js + MQTT Broker | Device management |
| **Mobile** | React Native BLE | Local device control |

---

## 📂 The .agent/ Directory in Detail

The `.agent/` directory is the **Control Plane** that makes vibe coding possible at scale.

### SOPs (Standard Operating Procedures)

Each SOP is a specialized instruction set for specific domains:

1. **UI_WORKFLOW.md**: How to build consistent UI
   - Component naming conventions
   - Tailwind class ordering
   - Accessibility requirements
   - Responsive design breakpoints

2. **BACKEND_WORKFLOW.md**: How to build robust APIs
   - Zod schema patterns
   - Error handling standards
   - Database migration protocols
   - Rate limiting rules

3. **DEBUG_WORKFLOW.md**: How to fix bugs systematically
   - Reproduction requirements
   - Root cause analysis template
   - Testing before fixing rule

4. **BILLING_WORKFLOW.md**: Midtrans integration specifics
   - Payment flow states
   - Webhook handling
   - Idempotency requirements
   - Receipt generation

5. **IOT_WORKFLOW.md**: Smart device management
   - Device pairing protocol
   - MQTT topic structure
   - Security key rotation
   - Firmware OTA updates

### Memory (Immutable Facts)

These files record decisions that won't change:

- **DECISION_LOG.md**: Why we chose Next.js over Nuxt, Drizzle over Prisma, etc.
- **API_CONTRACTS.md**: Documented API endpoints with examples
- **MIGRATION_LOG.md**: Every database change with rollback instructions

---

## 🔄 The Vibe Coding Workflow

Here's how an AI agent would work on Coolykos:

### Scenario: Adding a New Payment Method

1. **CEO (AGENT.md) reads the intent**: "Add DANA e-wallet payment option"

2. **Router directs to BILLING_WORKFLOW.md**: The AGENT.md recognizes this as a billing task

3. **AI reads SKILL.md**: Confirms Midtrans is our payment provider

4. **AI reads PROJECT_STATUS.md**: Sees we're on branch `feature/dana-payment`

5. **AI executes BILLING_WORKFLOW.md**:
   - Checks existing payment methods in `packages/api/src/routes/payments.ts`
   - Adds DANA to the Midtrans configuration
   - Updates the payment UI in `apps/web-dashboard/components/payments/`
   - Writes tests following the workflow rules

6. **AI updates PROJECT_STATUS.md**: Records what was done and what's next

---

## 🎓 Lessons from Coolykos

### What Works

1. **Strict Interface Contracts**: Hono RPC ensures the AI can't break API contracts
2. **Shared Packages**: Database schema in `packages/database` prevents drift
3. **SOP Specialization**: Separate workflows for UI, Backend, and Billing
4. **Immutable Memory**: Decision logs prevent the AI from second-guessing past choices

### Challenges Faced

1. **IoT Complexity**: Smart locks required custom SOPs for hardware-specific logic
2. **Payment Security**: Midtrans integration needed extra security rules
3. **Multi-Tenancy**: Supporting multiple property owners required careful database design

### Best Practices Derived

1. **One Role, One SOP**: Don't mix concerns in SOPs
2. **Document the "Why"**: Decision logs save hours of re-debate
3. **Shared Packages Rule**: Monorepo structure with shared types is essential
4. **Test in SOPs**: Every SOP should mandate test writing

---

## 🚀 Getting Started with Your Own Project

Want to structure your project like Coolykos?

1. **Copy the Structure**: Use the monorepo layout above
2. **Write Your SOPs**: Start with UI_WORKFLOW.md and BACKEND_WORKFLOW.md
3. **Define Your SKILL.md**: Lock in your tech stack
4. **Create AGENT.md**: Define your AI's persona and routing rules
5. **Update PROJECT_STATUS.md**: Keep it current before every session

---

> **Remember**: The goal isn't to copy Coolykos exactly. The goal is to create a **Control Plane** that constrains your AI agents to your specific domain and quality standards.

*Happy Vibe Coding!* 🚀
