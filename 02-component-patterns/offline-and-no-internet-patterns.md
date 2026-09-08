# Offline and No-Internet Patterns

Users expect apps to work even when connectivity is poor or absent. Offline and no-internet patterns keep the product useful and trusted in any condition.

---

## 1. Detecting Connection

- Monitor network status.
- Distinguish between offline, slow, and unstable connections.
- Show the connection state clearly without being alarming.
- Do not assume a single failure means the user is offline.

---

## 2. Offline Modes

### Read-only offline

- Cached content is still viewable.
- Searches and browsing use local data.
- Editing or creating is disabled with an explanation.

### Full offline

- Users can create, edit, and queue changes.
- Changes sync when the connection returns.
- Conflicts are handled on sync.

### Hybrid

- Some features work offline; others do not.
- Explain which features are limited.

---

## 3. Caching

- Cache important content for offline use.
- Let users choose what to cache.
- Sync in the background when online.
- Show what is cached and what is not.
- Expire or refresh stale cache.

---

## 4. Queue and Retry

- Queue actions that cannot be completed offline.
- Show the queue and status.
- Retry automatically when online.
- Let users cancel or edit queued actions.
- Notify when actions are completed or fail.

---

## 5. Sync and Conflicts

### Sync status

- Show the last sync time.
- Indicate if data is up to date.
- Show sync progress for large updates.

### Conflict handling

- Detect when the same data was changed in multiple places.
- Show the versions side by side.
- Let the user choose which version to keep.
- Provide a merge option where possible.

---

## 6. UX Patterns

### Offline banner

- A subtle banner showing the app is offline.
- “You’re offline. Some features are unavailable.”
- Do not block the whole UI.

### Cached badge

- Show that content is from cache.
- “Showing saved data from 2 hours ago.”

### Save for later

- Let users mark content for offline access.
- Show a list of saved items.

### Pending state

- Show actions that are waiting to sync.
- Use a badge or icon to indicate queued work.

### Retry controls

- One-tap retry for failed actions.
- Automatic retry with backoff.
- Don’t retry too aggressively; let the user decide.

---

## 7. Best Practices

- Design offline from the start, not as an afterthought.
- Be honest about what is and is not available offline.
- Preserve user work at all costs.
- Sync in the background, not during active use.
- Test on slow and flaky networks, not just offline.
- Avoid blocking the UI while waiting for sync.
- Provide clear feedback on queue and sync status.

---

## 8. Common Mistakes

- Crashing or hanging when offline.
- Losing user input when the connection drops.
- No indication of offline status.
- Blocking all features when only some need the internet.
- Not testing on real slow networks.
- Confusing error messages about network failures.
- No way to queue or retry actions.

---

## 9. Checklist

- [ ] Network status is detected and shown.
- [ ] Content is cached for offline use.
- [ ] Read, edit, and create work where appropriate.
- [ ] Actions are queued when offline.
- [ ] Sync is automatic and unobtrusive.
- [ ] Conflicts are shown and resolved by users.
- [ ] Offline limitations are explained clearly.
- [ ] Pending and synced states are visible.
- [ ] Retry is available for failed actions.
- [ ] User work is preserved on reconnection.
- [ ] App is tested on slow, flaky, and offline networks.
