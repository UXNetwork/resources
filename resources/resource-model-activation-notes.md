# commands for activating the resource model once deployed

```cleos push action eosio initresource '{"dataset_batch_size": 100, "oracle_consensus_threshold": 3, "period_start": "2021-04-25T00:00:00", "period_seconds": 86400, "initial_value_transfer_rate": 0.1, "max_pay_constant": 0.2947}' -p eosio@active```

```cleos push action eosio resactivate '{"active": true}' -p eosio@active```

Parameters:
- `dataset_batch_size` is the number of accounts whose usage data is sent per transaction. If this number is too high, transactions will exceed `max_transaction_cpu_usage`.

- `oracle_consensus_threshold` is the number of oracles that are required to submit the same data before inflation and distribution of tokens takes place.

- `period_start` is when the first inflation period starts. It may be in the past (the resource oracles will catch up), but should not be later than the time that `resactivate` is called.

- `period_seconds`, `initial_value_transfer_rate`, and `max_pay_constant` should not be changed except in testing.
