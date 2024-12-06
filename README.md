### **General Commands**
1. **Check Solana CLI Version:**
   ```powershell
   solana --version
   ```
2. **Set Cluster:**
   ```powershell
   solana config set --url <CLUSTER_URL>
   # Example for devnet:
   solana config set --url https://api.devnet.solana.com
   ```
3. **View Current Config:**
   ```powershell
   solana config get
   ```

---

### **Wallet and Keypair Management**
4. **Generate New Keypair:**
   ```powershell
   solana-keygen new --outfile C:\Users\<YourUsername>\.config\solana\my-keypair.json
   ```
5. **Recover Keypair from Seed Phrase:**
   ```powershell
   solana-keygen recover
   ```
6. **Show Keypair Details (Public Key):**
   ```powershell
   solana-keygen pubkey C:\Users\<YourUsername>\.config\solana\my-keypair.json
   ```
7. **View Wallet Balance:**
   ```powershell
   solana balance
   # Or specify a custom keypair:
   solana balance C:\Users\<YourUsername>\.config\solana\my-keypair.json
   ```

---

### **Airdrop Tokens**
8. **Request SOL Airdrop (Devnet/Testnet):**
   ```powershell
   solana airdrop <AMOUNT> C:\Users\<YourUsername>\.config\solana\id.json
   # Example for default keypair:
   solana airdrop 2
   ```

---

### **Transaction Management**
9. **Send SOL:**
   ```powershell
   solana transfer <RECIPIENT_PUBLIC_KEY> <AMOUNT> --from C:\Users\<YourUsername>\.config\solana\my-keypair.json
   ```
10. **Simulate Transaction:**
    ```powershell
    solana transfer <RECIPIENT_PUBLIC_KEY> <AMOUNT> --from C:\Users\<YourUsername>\.config\solana\my-keypair.json --simulate
    ```
11. **View Recent Transactions:**
    ```powershell
    solana transaction-history <PUBLIC_KEY>
    ```

---

### **Program Management**
12. **Deploy Program:**
    ```powershell
    solana program deploy C:\path\to\your\program.so
    ```
13. **Upgrade Program:**
    ```powershell
    solana program deploy C:\path\to\your\program.so --program-id <PROGRAM_ID>
    ```
14. **Show Program Logs:**
    ```powershell
    solana logs
    ```

---

### **Account Management**
15. **Create Account:**
    ```powershell
    solana create-account <ACCOUNT_PUBLIC_KEY> <LAMPORTS>
    ```
16. **View Account Details:**
    ```powershell
    solana account <ACCOUNT_PUBLIC_KEY>
    ```
17. **Close Account:**
    ```powershell
    solana close <ACCOUNT_PUBLIC_KEY> --recipient <RECIPIENT_PUBLIC_KEY>
    ```

---

### **Validator Commands**
18. **Create Vote Account:**
    ```powershell
    solana create-vote-account <VOTE_ACCOUNT_KEYPAIR> <VALIDATOR_IDENTITY_KEYPAIR> <COMMISSION>
    ```
19. **Stake Tokens:**
    ```powershell
    solana stake <STAKE_ACCOUNT_KEYPAIR> <VOTE_ACCOUNT_PUBLIC_KEY> --amount <AMOUNT>
    ```
20. **Withdraw Stake:**
    ```powershell
    solana withdraw-stake <STAKE_ACCOUNT_KEYPAIR> <DESTINATION_ACCOUNT_PUBLIC_KEY> <AMOUNT>
    ```

---

### **Token Management**
21. **Create Token:**
    ```powershell
    spl-token create-token
    ```
22. **Create Token Account:**
    ```powershell
    spl-token create-account <TOKEN_MINT_ADDRESS>
    ```
23. **Mint Tokens:**
    ```powershell
    spl-token mint <TOKEN_MINT_ADDRESS> <AMOUNT> <RECEIVER_ADDRESS>
    ```
24. **Transfer Tokens:**
    ```powershell
    spl-token transfer <TOKEN_MINT_ADDRESS> <AMOUNT> <RECIPIENT_PUBLIC_KEY>
    ```
25. **View Token Balances:**
    ```powershell
    spl-token accounts
    ```

---

### **Explorer and Utilities**
26. **Check Cluster Health:**
    ```powershell
    solana cluster-version
    ```
27. **Ping a Validator:**
    ```powershell
    solana ping <VALIDATOR_PUBLIC_KEY>
    ```
28. **Show Block Time:**
    ```powershell
    solana block-time <BLOCK_SLOT>
    ```

---

### **Environment Variables for Convenience**
For easier CLI usage, you can set the `SOLANA_KEYPAIR` environment variable to your default keypair path. This allows you to skip specifying the keypair file in commands.

#### To Set `SOLANA_KEYPAIR` in PowerShell:
```powershell
$env:SOLANA_KEYPAIR="C:\Users\<YourUsername>\.config\solana\id.json"
```
