---
description: >-
  AutoNode allows you to spin up a node seamlessly. It will automatically make
  sure your validator is active and signing as well as refresh your node on hard
  resets.
---

# AutoNode

## 1. Install Docker

**Step 1:** Spin up your instance on [AWS](first-time-setup/cloud-guides/aws.md) or [other providers](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides).

> It is recommended to go with Ubuntu or Amazon Linux as your operating system.

**Step 2:** [SSH](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides/aws#step-2-connecting-to-your-aws-instance) into the machine.

{% hint style="warning" %}
For other providers, like Digital Ocean or Vultr, you will get root access, therefore one needs to do some user setup to make the process work correctly.  
If you have root access follow the useradd process below first.
{% endhint %}

{% tabs %}
{% tab title="Ubuntu" %}
You will be logged on as root on your system and need to create a user to work with your auto\_node. _**You can choose every username you want**_, it will ask for a password and a password confirmation. \(please keep track of this password for future use!\)  
Then we need to add this user to the sudoers group \(to give them superuser privilege\).

```bash
useradd <your username>
passwd <your username>

usermod -aG sudo <your username>
```

Now logout of the root session \(type `exit`\), you should see a **login as** prompt, use here the username you just created.

```bash
login as: <your username>
```

After giving the password you can pick up the process of setting up auto\_node.
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
You need to open ports 6000 and 9000 on your instance in case you have a firewall. The firewall configuration varies from cloud to cloud provider. As an example, you can check how it is done on [Digital Ocean](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides/digital-ocean#firewall-setup) or [Vultr](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides/vultr#firewall-setup) or in any other of our [Cloud Guides](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides).
{% endhint %}

**Step 3:** Setup the machine \(Docker\):

{% tabs %}
{% tab title="Ubuntu" %}
```bash
sudo apt-get update -y && sudo apt install docker.io -y \
&& sudo usermod -aG docker $USER && sudo systemctl start docker \
&& sudo systemctl enable docker && exit
```
{% endtab %}

{% tab title="Amazon Linux" %}
```bash
sudo yum update -y && sudo yum install -y docker \
&& sudo usermod -aG docker $USER && sudo service docker start \
&& exit
```
{% endtab %}
{% endtabs %}

> For more details on how to setup docker, reference [this](https://docs.docker.com/engine/install/).

{% hint style="info" %}
The above command will exit out your SSH session \(needed for docker install\). SSH back into the machine.
{% endhint %}

## 2. Configure Validator

**Step 1:** Download the Harmony CLI:

```bash
curl -LO https://harmony.one/hmycli && mv hmycli hmy && chmod +x hmy
```

**Step 2:** Create a new key or import an existing key:

{% tabs %}
{% tab title="New Key" %}
```bash
./hmy keys add validator
```
{% endtab %}

{% tab title="Import Key" %}
```bash
./hmy keys import-private-key <private-key>
```
{% endtab %}
{% endtabs %}

**Step 3:** Install/Update AutoNode with:

```bash
bash <(curl -s -S -L https://raw.githubusercontent.com/harmony-one/auto-node/master/scripts/install.sh)
```

**Step 4:** Edit the `validator_config.json` file:

{% tabs %}
{% tab title="Edit Command" %}
```bash
nano validator_config.json
```
{% endtab %}

{% tab title="Example File" %}
```bash
{
    "validator-addr": "YOUR ONE1 ADDRESS",
    "name": "harmony_autonode",
    "website": "harmony.one",
    "security-contact": "Daniel-VDM",
    "identity": "auto-node",
    "amount": 10100,
    "min-self-delegation": 10000,
    "rate": 0.1,
    "max-rate": 0.75,
    "max-change-rate": 0.05,
    "max-total-delegation": 100000000.0,
    "details": "None"
}
```
{% endtab %}
{% endtabs %}

{% hint style="warning" %}
Note that the ONE address has to be in quotes
{% endhint %}

**Step 5:** Save and exit config by pressing **Ctrl + O** then hit enter, then press **Ctrl + X**:

**Step 6:** Fund your one1 account. For OSTN, the faucet is [here](https://faucet.os.hmny.io/).

## **3. Run AutoNode**

{% hint style="success" %}
Make sure you have the latest AutoNode version installed before running it. To download the latest version proceed to [Section 2](https://docs.harmony.one/home/validators/autonode-1#2-configure-validator) and execute Step 3.
{% endhint %}

**Step 1:** Run autonode with the following command:

```bash
./auto_node.sh run --auto-active --auto-reset --clean
```

**Step 2:** Answer the prompts with `Y` or `N` \(this process may take a minute\)

**Step 3:** After you see a loop of the node's header information \(labeled something like `This node's latest header at 2020-04-11 05:35:06.065816: { ...`\), detach from the AutoNode session by pressing **Ctrl + b**, _then_ **d** 

And that's it, you're done! Feel free to exit the SSH session. 

{% hint style="info" %}
Optional: once detached, export the node information with `./auto_node.sh export` and save it.
{% endhint %}

## 4. Maintenance

{% hint style="success" %}
Make sure you are [SSH](https://docs.harmony.one/home/validators/first-time-setup/cloud-guides/aws#step-2-connecting-to-your-aws-instance)-ed into your node's machine.

Make sure you are not attached to your AutoNode's session. If you are attached, detach by pressing **Ctrl + b**, _then_ **d.** 
{% endhint %}

### Viewing Node progress

If detached for AutoNode, attach with:

```bash
./auto_node.sh attach
```

### Manually creating a Validator

Once detached, create a validator with:

```bash
./auto_node.sh create-validator
```

> This might have to be done if the associated validator address had insufficient funds when AutoNode attempted to create a validator.

### Saving the BLS keys for reuse

Once detached, export the BLS key files with: 

```bash
./auto_node.sh export-bls . && mkdir -p harmony_bls_keys \
&& cp -R bls_keys/. harmony_bls_keys/
```

This ensures that the BLS key will be reused should you have to relaunch your node.

### Deactivating the Node for Maintenance

> This requires that you **DO NOT** run AutoNode with `--auto-active` option.

Once detached, deactivate your node with:

```bash
./auto_node.sh deactivate
```

Then once you are ready to validate again, activate your node with:

```bash
./auto_node.sh activate
```

### Killing your Node

Once detached, you can kill your node using:

```bash
./auto_node.sh kill
```

{% hint style="info" %}
More details about AutoNode can be found [here](https://github.com/harmony-one/auto-node). Feel free to contribute!
{% endhint %}

##  

