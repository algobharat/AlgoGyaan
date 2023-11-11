# Account 1 creates an asset called `rug` with a total supply
# of 1000 units and sets itself to the freeze/clawback/manager/reserve roles
sp = algod_client.suggested_params()
txn = transaction.AssetConfigTxn(
    sender=acct1.address,
    sp=sp,
    default_frozen=False,
    unit_name="rug",
    asset_name="Really Useful Gift",
    manager=acct1.address,
    reserve=acct1.address,
    freeze=acct1.address,
    clawback=acct1.address,
    url="https://path/to/my/asset/details",
    total=1000,
    decimals=0,
)

# Sign with secret key of creator
stxn = txn.sign(acct1.private_key)
# Send the transaction to the network and retrieve the txid.
txid = algod_client.send_transaction(stxn)
print(f"Sent asset create transaction with txid: {txid}")
# Wait for the transaction to be confirmed
results = transaction.wait_for_confirmation(algod_client, txid, 4)
print(f"Result confirmed in round: {results['confirmed-round']}")

# grab the asset id for the asset we just created
created_asset = results["asset-index"]
print(f"Asset ID created: {created_asset}")


FOR MORE DETAILS - [Official ASA Doc](https://developer.algorand.org/docs/get-details/asa/?from_query=asa#template-modal-overlay)
