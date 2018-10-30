### AEON WALLET CLI : command line Aeon wallet 

Aeon-Wallet-CLI needs to connect to an Aeon daemon to work correctly, either remotely or locally. 
This file is for listing all the commands of the Aeon wallet cli and what they are for. Section 1 is for running the wallet 
file via terminal or command prompt. Section 2 is for operational uses of the wallet-cli once connected and synced to a daemon.

## Section 1 : Commands for opening and running the CLI wallet


## Running Aeon-Wallet-CLI:

  aeon-wallet-cli [--wallet-file=<file>|--generate-new-wallet=<file>] [<COMMAND>]
  Example, if you want to run your cli wallet on a Public node (or a local node on your own network) you would need to CD 
  to the folder with Aeon-wallet-cli and run this command:
  
  ```aeon-wallet-cli --daemon-address 192.168.1.2:11181```
  
  You may get this warning message when connecting to public nodes: 
  
  ```Warning: using an untrusted daemon at 192.168.1.7:11181, privacy will be lessened```
  

## General options:

  `--help`
  
  Produce a list of commands that help determine how to run Aeon-Wallet-CLI
  
  `--version`
  
  Output version information of current Aeon-Wallet-CLI
  

## Wallet options:

  `--daemon-address arg`                  
  Use daemon instance at <host>:<port>
  
  `--daemon-host arg`                     
  Use daemon instance at host <arg> instead of localhost
                                          
  `--password arg`                        
  Wallet password (escape/quote as needed) 
                                          
  `--password-file arg`                   
  Wallet password file
  
  `--daemon-port arg (=0)`                
  Use daemon instance at port <arg> instead of 11181
                                          
  `--daemon-login arg`                   
  Specify username[:password] for daemon RPC client
                                          
  `--testnet`                             
  Use cli wallet for testnet only. Daemon must also be launched with --testnet flag
                                          
  `--stagenet`                            
  Use cli wallet for stagenet. Daemon must also be launched with --stagenet flag
                                          
  `--restricted-rpc`                      
  Restricts to view-only commands (USE this if running a public node!!!)
  
  `--shared-ringdb-dir arg` 
  (=/Users/jason/.shared-ringdb, /Users/jason/.shared-ringdb/testnet if 'testnet', 
  /Users/jason/.shared-ringdb/stagenet if 'stagenet') Set shared ring database path
  
  `--wallet-file arg`                     
  Use wallet file name <arg>
  
  `--generate-new-wallet arg`             
  Generate new wallet and save it to <Arg>
                                     
  `--generate-from-view-key arg`          
  Generate incoming-only wallet from view key
                                        
  `--generate-from-spend-key arg`         
  Generate deterministic wallet from spend key
  
  `--generate-from-keys arg`              
  Generate wallet from private keys
  
  `--generate-from-multisig-keys arg`     
  Generate a master wallet from multisig wallet keys
                                        
  `--generate-from-json arg`              
  Generate wallet from JSON format file
  
  `--mnemonic-language arg`               
  Language for mnemonic
  
  `--command arg`
  
  `--restore-deterministic-wallet`        
  Recover wallet using Electrum-style mnemonic seed
                                          
  `--restore-multisig-wallet`             
  Recover multisig wallet using Electrum-style mnemonic seed (Disabled currently)
                                          
  `--non-deterministic`                   
  Generate non-deterministic view and spend keys 
                                          
  `--electrum-seed arg`                   
  Specify Electrum seed for wallet recovery/creation
                                          
  `--trusted-daemon`                      
  Enable commands which rely on a trusted daemon (use this to remove the trusted daemon warning only when you know the operator of the daemon)
                                          
  `--untrusted-daemon`                    
  Disable commands which rely on a trusted daemon 
                                          
  `--allow-mismatched-daemon-version`     
  Allow communicating with a daemon that uses a different RPC version (not really recommended)
                                          
  `--restore-height arg (=0)`             
  Restore from specific blockchain height
  
  `--do-not-relay`                        
  The newly created transaction will not be relayed to the Aeon network
                                          
  `--create-address-file`                 
  Create an address file for new wallets
  
  `--subaddress-lookahead arg`            
  Set subaddress lookahead sizes to <major>:<minor> 
                                          
  `--use-english-language-names`          
  Display English language names
  
  `--log-file arg`                        
  Specify log file name
  
  `--log-level arg`                       
  0-4 or categories
  
  `--max-log-file-size arg (=104850000)`  
  Specify maximum log file size [B]
  
  `--max-log-files arg (=50)`             
  Specify maximum number of rotated log files to be saved (no limit by setting to 0) 
                                          
  `--max-concurrency arg (=1)`           
  Max number of threads to use for a parallel job
                                          
  `--config-file arg`                     
  Config file
  
  
  ### Section 2 : Synced wallet commands
  
  ## Account related commands:
  
    ```
    account new <label text with white spaces allowed>
    account switch <index> 
    account label <index> <label text with white spaces allowed>
    account tag <tag_name> <account_index_1> [<account_index_2> ...]
    account untag <account_index_1> [<account_index_2> ...]
    account tag_description <tag_name> <description>
    ```
    
  ## Standard commands:
  
 ```
  address [ new <label text with white spaces allowed> | all | <index_min> [<index_max>] | label <index> <label text with white spaces allowed>]
  address_book [(add ((<address> [pid <id>])|<integrated address>) [<description possibly with whitespaces>])|(delete <index>)]
  balance [detail]
  bc_height
  blackball <output public key> | <filename> [add]
  blackballed <output public key>
  check_reserve_proof <address> <signature_file> [<message>]
  check_spend_proof <txid> <signature_file> [<message>]
  check_tx_key <txid> <txkey> <address>
  check_tx_proof <txid> <address> <signature_file> [<message>]
  donate [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <amount> [<payment_id>]
  encrypted_seed
  export_key_images <file>
  export_outputs <file>
  get_description
  get_reserve_proof (all|<amount>) [<message>]
  get_spend_proof <txid> [<message>]
  get_tx_key <txid>
  get_tx_note <txid>
  get_tx_proof <txid> <address> [<message>]
  help [<command>]
  import_key_images <file>
  import_outputs <file>
  incoming_transfers [available|unavailable] [verbose] [index=<N1>[,<N2>[,...]]]
  integrated_address [<payment_id> | <address>]
  locked_transfer [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <addr> <amount> <lockblocks> [<payment_id>]
  password
  payment_id
  payments <PID_1> [<PID_2> ... <PID_N>]
  print_ring <key_image> | <txid>
  refresh
  rescan_bc
  rescan_spent
  save
  save_bc
  save_known_rings
  save_watch_only
  seed
  set <option> [<value>]
  set_daemon <host>[:<port>] [trusted|untrusted]
  set_description [free text note]
  set_log <level>|{+,-,}<categories>
  set_ring <filename> | ( <key_image> absolute|relative <index> [<index>...] )
  set_tx_note <txid> [free text note]
  show_transfer <txid>
  show_transfers [in|out|pending|failed|pool] [index=<N1>[,<N2>,...]] [<min_height> [<max_height>]]
  sign <file>
  sign_transfer [export_raw]
  spendkey
  start_mining [<number_of_threads>] [bg_mining] [ignore_battery]
  status
  stop_mining
  submit_transfer
  sweep_all [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <address> [<payment_id>]
  sweep_below <amount_threshold> [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <address> [<payment_id>]
  sweep_single [<priority>] [<ring_size>] <key_image> <address> [<payment_id>]
  sweep_unmixable
  transfer [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <address> <amount> [<payment_id>]
  transfer_original [index=<N1>[,<N2>,...]] [<priority>] [<ring_size>] <address> <amount> [<payment_id>]
  unblackball <output public key>
  unspent_outputs [index=<N1>[,<N2>,...]] [<min_amount> [<max_amount>]]
  verify <filename> <address> <signature>
  version
  viewkey
  wallet_info
  ```
  
