# Go · gRPC · Hexagonal — Cheat Sheet

A single-page reference for building Go microservices with gRPC and Hexagonal Architecture (Ports & Adapters). Annotations are written in Thai (ภาษาไทย).

**Live site →** https://grpc-cheat-sheet.github.io

---

## What's covered

| Topic | Sections |
|---|---|
| **Go Basics** | Struct & Method, Interface, Slice & Map, Constructor Pattern, Defer & Cleanup, Type Embedding, Functional Options |
| **Concurrency** | Goroutine & Channel, Context & WaitGroup, Mutex & RWMutex, errgroup parallel tasks |
| **Error Handling** | Custom Error & Sentinel, `errors.Is` / `errors.As` / `%w` |
| **Protocol Buffers 3** | Service definition, Message types, Streaming types, Field type mapping |
| **gRPC Server** | Server setup, Interceptor (middleware), Status errors, Status codes reference |
| **gRPC Client** | Client connection, Metadata (headers) |
| **Hexagonal Architecture** | Domain Core, Ports, Adapters, Folder structure, Dependency rule |
| **Full Code Examples** | Domain entity, Output port, Use case, FCM adapter (secondary) |
| **Wire Up & Testing** | Dependency injection in `main.go`, gRPC handler (primary adapter), Unit test with mock port, Quick commands |

## Usage frequency legend

| Indicator | Meaning |
|---|---|
| 🟢 ใช้ทุกวัน | Used daily — you will definitely encounter this |
| 🟡 ใช้บ้าง | Used sometimes — depends on the task |
| 🔴 ใช้น้อย | Rarely used — special cases only |

## Tech stack

- **Go 1.22+**
- **gRPC / proto3** (`google.golang.org/grpc`, `google.golang.org/protobuf`)
- **Hexagonal Architecture** — Ports & Adapters pattern
- **errgroup** (`golang.org/x/sync/errgroup`)

## Local development

No build step required — it's a single HTML file.

```bash
# open directly
open index.html

# or serve with any static server
npx serve .
python3 -m http.server 8080
```

## Project structure

```
grpc-cheat-sheet.github.io/
├── index.html   # entire cheat sheet
└── README.md
```
