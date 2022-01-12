check-helium-bannedlist
=======================

Allows you to check if your hotspot is banned by Helium Inc for violation of non-existing rules.

Requirements:
- Erlang 24: https://www.erlang-solutions.com/downloads/
- Public key of your hotspot in binary format
- This repository

How to extract your public key:
- SSH to your hotspot and login to the remote_console with `sudo docker exec -it miner miner remote_console`
- Execute `rp(libp2p_crypto:pubkey_to_bin(libp2p_crypto:b58_to_pubkey("ADDRESS_OF_YOUR_MINER"))).`

How to use this repo:
- modify src/test_app.erl and add your public key where it says PUT_YOUR_PUBLIC_KEY_HERE
- `wget https://s3.amazonaws.com/rebar3/rebar3 && chmod +x rebar3`
- `./rebar3 shell`
- `application:start(test).`
- ignore the crashes
