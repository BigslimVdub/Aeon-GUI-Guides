## This file is for documenting all the daemon commands for Aeon CLI daemon. 

If you want to run a public node with the blockchain on drive F:\ you would use this command:

```
aeond.exe --rpc-bind-ip 0.0.0.0 --confirm-external-bind --restricted-rpc --data-dir=F:\aeon\lmdb
```

## Section 1: Running AeonD with terminal/CMD prompt:

```
Aeon 'Sophia' (v0.12.6.0-master-release)

Usage: aeond.exe [options|settings] [daemon_command...]

Options:
  --help                                Produce help message
  --version                             Output version information
  --os-version                          OS for which this executable was
                                        compiled
  --config-file arg (=C:\Users\YourUserName\AppData\Roaming\aeon\aeon.conf, C:\Users\YourUserName\AppData\Roaming\aeon\testnet\aeon.conf if 'testnet', C:\Users\YourUserName\AppData\Roaming\aeon\stagenet\aeon.conf if 'stagenet')
                                        Specify configuration file
  --install-service                     Install Windows service
  --uninstall-service                   Uninstall Windows service
  --start-service                       Start Windows service
  --stop-service                        Stop Windows service

Settings:
  --log-file arg (=C:\Users\YourUserName\AppData\Roaming\aeon\aeon.log, C:\Users\YourUserName\AppData\Roaming\aeon\testnet\aeon.log if 'testnet', C:\Users\YourUserName\AppData\Roaming\aeon\stagenet\aeon.log if 'stagenet')
                                        Specify log file
  --log-level arg
  --max-log-file-size arg (=104850000)  Specify maximum log file size [B]
  --max-log-files arg (=50)             Specify maximum number of rotated log
                                        files to be saved (no limit by setting
                                        to 0)
  --max-concurrency arg (=0)            Max number of threads to use for a
                                        parallel job
  --zmq-rpc-bind-ip arg (=127.0.0.1)    IP for ZMQ RPC server to listen on
  --zmq-rpc-bind-port arg (=11182, 21182 if 'testnet', 31182 if 'stagenet')
                                        Port for ZMQ RPC server to listen on
  --data-dir arg (=C:\ProgramData\aeon, C:\ProgramData\aeon\testnet if 'testnet', C:\ProgramData\aeon\stagenet if 'stagenet')
                                        Specify data directory
  --test-drop-download                  For net tests: in download, discard ALL
                                        blocks instead checking/saving them
                                        (very fast)
  --test-drop-download-height arg (=0)  Like test-drop-download but discards
                                        only after around certain height
  --testnet                             Run on testnet. The wallet must be
                                        launched with --testnet flag.
  --stagenet                            Run on stagenet. The wallet must be
                                        launched with --stagenet flag.
  --enforce-dns-checkpointing           checkpoints from DNS server will be
                                        enforced
  --prep-blocks-threads arg (=4)        Max number of threads to use when
                                        preparing block hashes in groups.
  --fast-block-sync arg (=1)            Sync up most of the way by using
                                        embedded, known block hashes.
  --show-time-stats arg (=0)            Show time-stats when processing
                                        blocks/txs and disk synchronization.
  --block-sync-size arg (=0)            How many blocks to sync at once during
                                        chain synchronization (0 = adaptive).
  --check-updates arg (=notify)         Check for new versions of Aeon:
                                        [disabled|notify|download|update]
  --fluffy-blocks                       Relay blocks as fluffy blocks
                                        (obsolete, now default)
  --no-fluffy-blocks                    Relay blocks as normal blocks
  --test-dbg-lock-sleep arg (=0)        Sleep time in ms, defaults to 0 (off),
                                        used to debug before/after locking
                                        mutex. Values 100 to 1000 are good for
                                        tests.
  --offline                             Do not listen for peers, nor connect to
                                        any
  --disable-dns-checkpoints             Do not retrieve checkpoints from DNS
  --max-txpool-size arg (=648000000)    Set maximum txpool size in bytes.
  --extra-messages-file arg             Specify file for extra messages to
                                        include into coinbase transactions
  --start-mining arg                    Specify wallet address to mining for
  --mining-threads arg                  Specify mining threads count
  --bg-mining-enable                    enable/disable background mining
  --bg-mining-ignore-battery            if true, assumes plugged in when unable
                                        to query system power status
  --bg-mining-min-idle-interval arg     Specify min lookback interval in
                                        seconds for determining idle state
  --bg-mining-idle-threshold arg        Specify minimum avg idle percentage
                                        over lookback interval
  --bg-mining-miner-target arg          Specify maximum percentage cpu use by
                                        miner(s)
  --db-type arg (=lmdb)                 Specify database type, available: lmdb
  --db-sync-mode arg (=fast:async:1000) Specify sync option, using format
                                        [safe|fast|fastest]:[sync|async]:[nbloc
                                        ks_per_sync].
  --db-salvage                          Try to salvage a blockchain database if
                                        it seems corrupted
  --p2p-bind-ip arg (=0.0.0.0)          Interface for p2p network protocol
  --p2p-bind-port arg (=11180, 21180 if 'testnet', 31180 if 'stagenet')
                                        Port for p2p network protocol
  --p2p-external-port arg (=0)          External port for p2p network protocol
                                        (if port forwarding used with NAT)
  --allow-local-ip                      Allow local ip add to peer list, mostly
                                        in debug purposes
  --add-peer arg                        Manually add peer to local peerlist
  --add-priority-node arg               Specify list of peers to connect to and
                                        attempt to keep the connection open
  --add-exclusive-node arg              Specify list of peers to connect to
                                        only. If this option is given the
                                        options add-priority-node and seed-node
                                        are ignored
  --seed-node arg                       Connect to a node to retrieve peer
                                        addresses, and disconnect
  --hide-my-port                        Do not announce yourself as peerlist
                                        candidate
  --no-igd                              Disable UPnP port mapping
  --out-peers arg (=-1)                 set max number of out peers
  --in-peers arg (=-1)                  set max number of in peers
  --tos-flag arg (=-1)                  set TOS flag
  --limit-rate-up arg (=-1)             set limit-rate-up [kB/s]
  --limit-rate-down arg (=-1)           set limit-rate-down [kB/s]
  --limit-rate arg (=-1)                set limit-rate [kB/s]
  --save-graph                          Save data for dr aeon
  --rpc-bind-port arg (=11181, 21181 if 'testnet', 31181 if 'stagenet')
                                        Port for RPC server
  --rpc-restricted-bind-port arg        Port for restricted RPC server
  --restricted-rpc                      Restrict RPC to view only commands and
                                        do not return privacy sensitive data in
                                        RPC calls
  --bootstrap-daemon-address arg        URL of a 'bootstrap' remote daemon that
                                        the connected wallets can use while
                                        this daemon is still not fully synced
  --bootstrap-daemon-login arg          Specify username:password for the
                                        bootstrap daemon login
  --rpc-bind-ip arg (=127.0.0.1)        Specify IP to bind RPC server
  --rpc-login arg                       Specify username[:password] required
                                        for RPC server
  --confirm-external-bind               Confirm rpc-bind-ip value is NOT a
                                        loopback (local) IP
  --rpc-access-control-origins arg      Specify a comma separated list of
                                        origins to allow cross origin resource
                                        sharing
                                        
 ```                                       



## Section 2: Basic Daemon commands

```
Aeon 'Sophia' (v0.12.6.0-master-release)
Commands:
  alt_chain_info
  ban <IP> [<seconds>]
  bans
  bc_dyn_stats <last_block_count>
  diff
  exit
  flush_txpool [<txid>]
  hard_fork_info
  help [<command>]
  hide_hr
  in_peers <max_number>
  is_key_image_spent <key_image>
  limit [<kB/s>]
  limit_down [<kB/s>]
  limit_up [<kB/s>]
  out_peers <max_number>
  output_histogram [@<amount>] <min_count> [<max_count>]
  print_bc <begin_height> [<end_height>]
  print_block <block_hash> | <block_height>
  print_cn
  print_coinbase_tx_sum <start_height> [<block_count>]
  print_height
  print_pl
  print_pl_stats
  print_pool
  print_pool_sh
  print_pool_stats
  print_status
  print_tx <transaction_hash> [+hex] [+json]
  relay_tx <txid>
  save
  set_log <level>|<{+,-,}categories>
  show_hr
  start_mining <addr> [<threads>] [do_background_mining] [ignore_battery]
  start_save_graph
  status
  stop_daemon
  stop_mining
  stop_save_graph
  sync_info
  unban <IP>
  update (check|download)
  version
  ```
  
 
