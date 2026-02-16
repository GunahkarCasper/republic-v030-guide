RepublicAI v0.3.0 Validator Upgrade Guide (Cosmovisor)
This guide provides step-by-step instructions to upgrade your RepublicAI validator node to v0.3.0 on the raitestnet_77701-1 network using Cosmovisor.

Upgrade Specifications
Upgrade Height: 326250

Upgrade Name: v0.3.0

Binary Target: republicd-linux-amd64

Step-by-Step Installation
1. Prepare the Upgrade Directory
Create the necessary folder structure for Cosmovisor to recognize the new version.

```bash
mkdir -p $HOME/.republicd/cosmovisor/upgrades/v0.3.0/bin
```

2. Navigate to the Target Folder
Move into the newly created bin directory.
```bash
cd $HOME/.republicd/cosmovisor/upgrades/v0.3.0/bin
```

3. Download the New Binary
Fetch the official v0.3.0 release from the RepublicAI GitHub repository.
```bash
wget -O republicd https://github.com/RepublicAI/networks/releases/download/v0.3.0/republicd-linux-amd64
```

4. Verify Integrity (SHA256 Checksum)
Ensure the downloaded file is not corrupted or tampered with.
```bash
echo "bf0c88fda3ec40d8b991f87105c46ac6ddd7901d735213748de2c14e1b63a2a5  republicd" | sha256sum -c
```
Expected Output: republicd: OK

5. Set Execution Permissions
Grant the binary the necessary permissions to run.
```bash
chmod +x republicd
```

6. Verify Version
Confirm that the binary is indeed the correct version.
```bash
./republicd version
```

 Post-Upgrade Protocol
Once these steps are completed, Cosmovisor will automatically switch to the v0.3.0 binary exactly at block 326250.No manual restart will be required if Cosmovisor is running as a background service.

Post-Upgrade Verification
After the network reaches the upgrade height, you can verify your active version with:

```bash
/root/.republicd/cosmovisor/current/bin/republicd version
```

⚠️ Important Notes
Non-Cosmovisor Users: If you are not using Cosmovisor, you must perform these steps manually ONLY AFTER block 326250 is reached.

GPU Support: This version enables GPU computing. Ensure your NVIDIA drivers are correctly installed (nvidia-smi) to benefit from aggressive rewards.

Twitter: https://x.com/GunahkarCasper

