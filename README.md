# otel-prometheus-remote-write-receiver

1. Start collector and prometheus

    ```sh
    docker-compose up -d
    ```

1. Observe collector logs. See that `go_gc_heap_allocs_bytes_total` is written once.

    ```sh
    docker logs -f collector
    ```

1. Wait and observe that no new values of `go_gc_heap_allocs_bytes_total` are written.

1. Observe the value of `go_gc_heap_allocs_bytes_total` over time at <http://localhost:9090/query?g0.expr=go_gc_heap_allocs_bytes_total> and see that is changing.

1. Optional: Observe prometheus logs

    ```sh
    docker logs -f prometheus
    ```

1. Stop Everything

    ```sh
    docker-compose down -v
    ```
