check-helium-bannedlist
=======================

Allows you to check if your hotspot is banned by Helium Inc for violation of non-existing rules.

Requirements:
- Erlang 24: https://www.erlang-solutions.com/downloads/
- Public key of your hotspot in binary format
- This repository

How to extract your public key:
- SSH to your hotspot (if possible) and login to the remote_console with "sudo docker exec -it miner miner remote_console"
- Execute "rp(libp2p_crypto:pubkey_to_bin(libp2p_crypto:b58_to_pubkey("<address>")))."

How to use this repo:
- git clone
- modify src/test_app.erl and add your public key
- chmod +x rebar3
- ./rebar3 shell
- application:start(test).
- ignore the crashes
