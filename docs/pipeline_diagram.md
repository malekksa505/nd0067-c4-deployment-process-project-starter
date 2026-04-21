---

## Pipeline Diagram

```
┌─────────────┐
│   Push to   │
│   GitHub    │
└──────┬──────┘
       │
       ▼
┌─────────────────────────────┐
│      Build Job              │
│  - Install Dependencies     │
│  - Frontend & API           │
└──────┬──────────────────────┘
       │
       ▼
┌─────────────────────────────┐
│   Manual Approval           │
│   (master branch only)      │
└──────┬──────────────────────┘
       │
       ▼
┌─────────────────────────────┐
│      Deploy Job             │
│  - Build & Deploy API       │
│  - Build & Deploy Frontend  │
└─────────────────────────────┘
       │
       ├──────────────┐
       ▼              ▼
┌─────────────┐  ┌─────────────┐
│ S3 Bucket   │  │  Elastic    │
│  Frontend   │  │  Beanstalk  │
└─────────────┘  └─────────────┘
```

---