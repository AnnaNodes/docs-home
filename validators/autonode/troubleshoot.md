---
description: Some steps for troubleshooting your AutoNode
---

# Troubleshoot

{% hint style="success" %}
If you encounter any issue you cannot solve, feel free to reach out to us at **autonode@harmony.one**.
{% endhint %}

## Inspect AutoNode logs

All AutoNode generated logs are saved in `$HOME/.hmy` when you execute the following command:

```bash
ls $HOME/.hmy/*.log
```

You should see 2 files, `autonode_monitor.log` and `autonode_node.log`. Inspect those two files with your favorite command-line editor \(i.e: `vim`\) to see where things might have gone wrong. 

You might also find it useful to inspect the Harmony Node logs. You can do so with the following command:

```bash
vim $HOME/harmony_node/latest/zero*.log
```

> You can change the `vim` part of the command for your favorite text editor.

## Restart the Harmony Node

You can restart the Harmony Node service with the following command:

```bash
auto-node node restart
```

You can check the status of the service with the following command:

```bash
auto-node node status
```

You can fetch the Harmony Node version with the following command:

```bash
auto-node node version
```

## Restart the AutoNode Monitor

You can restart the monitor service with the following command:

```bash
auto-node monitor restart
```

You can check the status of the service with the following command:

```bash
auto-node monitor status
```

## Re-Authenticating your validator wallet

If your encrypted passphrase for your validator is ever invalidated, you can re-encrypt and save it with the following command:

```bash
auto-node auth-wallet
```

## Optimize Operating System

You can choose to optimize your operating system for running a harmony node. The optimizations, or tunes, are made to keep your node safe but also lifts some default restrictions. Here is the command to tune your OS with AutoNode:

```bash
auto-node tune kernel --save
```

> This will tune the kernel and the `--save` option will make it persistant. If you do not have the `--save` option, the tunes will only last untill the system is rebooted \(by you or your VPS\).  
>   
> Note that all the tunes will be displayed and confirmation asked before applying the tunes.

You can also tune/optimize your network settings with the following command:

```bash
auto-node tune network --save
```

## Restoring Operating System from Optimization

If you want to revert the optimization/tune applied by AutoNode, you can do so by running the following command:

```bash
auto-node tune restore
```

> Note that you can run the command muliple times to restore previous tunes chronologically. Moveover, the







