# K8s in a Box — Scenario Brief

- Generated: `2025-10-26 21:31:07 UTC`
- Difficulty: **easy**
- Seed: `1761514267`

## Setup
```bash
make cluster
make challenge DIFFICULTY=easy SEED=1761514267
make status
```

## Your Objective
Bring the in-cluster service **app** to a healthy state and pass verification:

```bash
make verify
```

## Acceptance Criteria
- The `app` container should **start** without CrashLoopBackOff due to missing env/config.
- `kubectl get pvc -n kbox` shows **Bound** for `app-pvc`.
- `kubectl get pods -n kbox` shows Pods **Ready**.
- `kubectl get svc,ep -n kbox` shows **endpoints** for `app`.
- From `net-debug`, `wget -qO- app.kbox.svc.cluster.local/health` returns **200 OK** (or `/`).

## Hints (optional)
- Compare labels and selectors between Deployment and Service.
- Verify `targetPort` vs containerPort.
- Check Events for probe or volume mount failures.
- If traffic times out, consider NetworkPolicies.
- Use `kubectl exec -n kbox -it net-debug -- sh` to curl/wget the service.