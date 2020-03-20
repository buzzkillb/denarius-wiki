---
title: "Commands"
date: 2020-03-04T00:17:05-08:00
---
## Native QT and daemon Commands
`addmultisigaddress <nrequired> <'["key","key"]'> [account]`  
`addnode <node> <add|remove|onetry|ban>`  
`addredeemscript <redeemScript> [account]`  
`anoninfo [recalculate]`  
`anonoutputs [systemTotals] [show_immature_outputs]`  
`backupwallet <destination>`  
`checkwallet`  
`clearwallettransactions`  
`createmultisig <nrequired> <'["key","key"]'>`  
`createrawtransaction [{"txid":txid,"vout":n},...] {address:amount,...}`  
`decoderawtransaction <hex string>`  
`decodescript <hex string>`  
`disconnectnode "node"`  
`dumpbootstrap "destination" "blocks"`  
`dumpprivkey <denariusaddress>`  
`dumpwallet <filename>`  
`encryptwallet <passphrase>`  
`estimateanonfee <amount> <ring_size> [narration]`  
`fetchbalance`  
`fortunastake "command"... ( "passphrase" )`  
`getaccount <denariusaddress>`  
`getaccountaddress <account>`  
`getaddednodeinfo <dns> [node]`  
`getaddressesbyaccount <account>`  
`getbalance ( "account" minconf includeWatchonly )`  
`getbestblockhash`  
`getblock "blockhash" ( verbosity )`   
`getblock <hash> [txinfo]`  
`getblockbynumber <number> [txinfo]`  
`getblockchaininfo`  
`getblockcount`  
`getblockhash <index>`  
`getblockheader "hash" ( verbose )`  
`getblocktemplate [params]`  
`getcheckpoint`  
`getconnectioncount`  
`getdifficulty`  
`gethashespersec`  
`getinfo`  
`getmininginfo`  
`getnettotals`  
`getnetworkinfo`  
`getnewaddress [account]`  
`getnewpubkey [account]`  
`getnewstealthaddress [label]`  
`getpeerinfo`  
`getpoolinfo`  
`getrawmempool`  
`getrawtransaction <txid> [verbose=0]`  
`getreceivedbyaccount <account> [minconf=1]`  
`getreceivedbyaddress <denariusaddress> [minconf=1]`  
`getstakinginfo`  
`getsubsidy [nTarget]`  
`gettransaction <txid>`  
`gettxout "txid" n ( includemempool )`  
`getwork [data]`  
`getworkex [data, coinbase]`  
`help [command]`  
`importaddress <address> [label] [rescan=true]`  
`importprivkey <denariusprivkey> [label] [rescan=true]`  
`importstealthaddress <scan_secret> <spend_secret> [label]`  
`importwallet <filename>`  
`jupiterduo`  
`jupiterduopod`  
`jupitergetblock`  
`jupitergetstat`  
`jupiterpod`  
`jupiterupload`  
`jupiterversion`  
`keypoolrefill [new-size]`  
`listaccounts [minconf=1]`  
`listaddressgroupings`  
`listreceivedbyaccount [minconf=1] [includeempty=false]`  
`listreceivedbyaddress ( minconf includeempty includeWatchonly)`  
`listsinceblock [blockhash] [target-confirmations]`  
`liststealthaddresses [show_secrets=0]`  
`listtransactions [account] [count=10] [from=0] [watchonly=false] [show_coinstake=1]`  
`listunspent [minconf=1] [maxconf=9999999] ["address",...]`  
`makekeypair [prefix]`  
`fortunastake "command"... ( "passphrase" )`  
`move <fromaccount> <toaccount> <amount> [minconf=1] [comment]`  
`ping`  
`proofofdata`  
`reloadanondata `  
`repairwallet`  
`resendtx`  
`reservebalance [<reserve> [amount]]`  
`scanforalltxns [fromHeight]`  
`searchrawtransactions <address> [verbose=1] [skip=0] [count=100]`  
`sendalert <message> <privatekey> <minver> <maxver> <priority> <id> [cancelupto]`  
`sendanontoanon <stealth_address> <amount> <ring_size> [narration] [comment] [comment-to]`  
`sendanontod <stealth_address> <amount> <ring_size> [narration] [comment] [comment-to]`  
`senddtoanon <stealth_address> <amount> [narration] [comment] [comment-to]`  
`sendfrom <fromaccount> <todenariusaddress> <amount> [minconf=1] [comment] [comment-to] [narration]`   
`sendmany <fromaccount> {address:amount,...} [minconf=1] [comment]`  
`sendrawtransaction <hex string>`  
`sendtoaddress <denariusaddress> <amount> [comment] [comment-to] [narration]`  
`setaccount <denariusaddress> <account>`  
`setbestblockbyheight <height>`  
`setdebug <type> <on|off>`  
`settxfee <amount>`  
`signmessage <denariusaddress> <message>`  
`signrawtransaction <hex string> [{"txid":txid,"vout":n,"scriptPubKey":hex},...] [<privatekey1>,...] [sighashtype="ALL"]`  
`smsgaddkey <address> <pubkey>`  
`smsgbuckets [stats|dump]`  
`smsgdisable`  
`smsgenable`  
`smsggetpubkey <address>`  
`smsginbox [all|unread|clear]`  
`smsglocalkeys [whitelist|all|wallet|recv <+/-> <address>|anon <+/-> <address>]`  
`smsgoptions [list|set <optname> <value>]`  
`smsgoutbox [all|clear]`  
`smsgscanbuckets`  
`smsgscanchain`   
`smsgsend <addrFrom> <addrTo> <message>`  
`smsgsendanon <addrTo> <message>`  
`stop <detach>`  
`submitblock <hex data> [optional-params-obj]`  
`txnreport [collate_amounts] [show_key_images]`  
`validateaddress <denariusaddress>`  
`validatepubkey <denariuspubkey>`  
`verifymessage <denariusaddress> <signature> <message>`  
