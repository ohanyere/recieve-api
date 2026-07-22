# Runbook

## Service

- Name: `recieve-api`
- Team: `Payments`
- Owner: `mooref068@gmail.com`
- Cost center: `payments`

## First Checks

```bash
kubectl get rollout recieve-api -n recieve-api-dev
kubectl get pods -l app.kubernetes.io/name=recieve-api -n recieve-api-dev
kubectl logs -l app.kubernetes.io/name=recieve-api -n recieve-api-dev
```

## Health

```bash
curl https://recieve-api.dev.platform.ohanyere.internal/healthz
curl https://recieve-api.dev.platform.ohanyere.internal/readyz
curl https://recieve-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo recieve-api -n recieve-api-dev
```

Escalate to `Payments` through `mooref068@gmail.com` if rollback does not restore service.
