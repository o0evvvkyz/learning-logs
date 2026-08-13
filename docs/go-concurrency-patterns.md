# Go Concurrency Patterns

Notes from today's reading on goroutines and channels.

## Worker pools
- Use `sync.WaitGroup` to wait for all workers.
- Buffered channels help limit concurrency.
- Always close the results channel after workers finish.

## Select with timeouts
- `select` + `time.After` prevents blocking forever.
- Default case for non-blocking sends/receives.

## Pitfalls
- Don't share memory; communicate via channels.
- Beware of goroutine leaks — cancel via context.

Next: explore `errgroup` for fan-out/fan-in.
