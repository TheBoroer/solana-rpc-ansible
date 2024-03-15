validator:
        /home/solana/validator.sh
start:
        sudo systemctl start sol.service
stop:
        sudo systemctl stop sol.service
restart:
        sudo systemctl stop sol.service
        sudo systemctl start sol.service
download-snapshot:
        #python3 /mnt/snapshot-finder.py --snapshot_path /mnt/solana-snapshots --version=$(solana --version | awk '{print $2}') -t 10 --sleep 10
        python3 /mnt/snapshot-finder.py --snapshot_path /mnt/solana-snapshots -t 10 --sleep 10
logs:
        tail -f /mnt/logs/solana-validator.log
monitor:
        solana-validator --ledger /mnt/solana-ledger/ monitor
test-http:
        curl http://localhost:8899  -X POST -H "Content-Type: application/json" -d '{"jsonrpc":"2.0","id":1, "method":"getSlot"}'
test-ws:
        wscat --connect ws://localhost:8900/ -w 1 -x '{"jsonrpc":"2.0", "id":1, "method":"slotSubscribe"}'
