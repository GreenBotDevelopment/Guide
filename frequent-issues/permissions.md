---
description: Fix "Green-bot can't join or speak in my voice channel" - Connect, Speak, Move Members and channel overrides.
---

# Permissions

{% hint style="info" %}
**Not a server admin?** Send this page to someone who has the **Manage Channels** or **Manage Roles** permission. They only need a few minutes.
{% endhint %}

## What is wrong?

| What you see | Cause | Fix |
| --- | --- | --- |
| Green-bot can't join, or says it can't speak | Missing **Connect** or **Speak** | [Section 1](permissions.md#1-connect-and-speak) |
| Green-bot can't join and the voice channel is full | The channel is at its user limit | [Section 2](permissions.md#2-the-voice-channel-is-full) |
| You gave the permission but it still fails | A channel setting denies the bot | [Section 3](permissions.md#3-the-permission-is-given-but-it-still-fails) |

## Fastest fix: re-invite Green-bot

You don't need to kick the bot. Re-invite it with the link below and it keeps all its settings:

[Re-invite Green-bot 1](https://discord.com/oauth2/authorize?client_id=783708073390112830&scope=bot+applications.commands&permissions=322268168)

This link asks for the Administrator permission, which covers every permission on this page, including channel-level ones. If you prefer to give only what is needed, follow the sections below.

## 1. Connect and Speak

1. Click the **gear icon** (Edit Channel) next to your voice channel.

![](<../.gitbook/assets/image (6).png>)

2. Open **Permissions**.

![](<../.gitbook/assets/image (32).png>)

3. Click the **+** and add **Green-bot**.

![](<../.gitbook/assets/image (11).png>)

4. Scroll down and enable **Connect** and **Speak** (green check).

![](<../.gitbook/assets/image (14).png>)

## 2. The voice channel is full

When a voice channel has a **User Limit** and every slot is taken, Discord only lets a bot in if it has the **Move Members** permission. Pick one fix:

* **Free a slot:** ask someone to leave, then use `/play` again.
* **Raise the limit:** Edit Channel → **Overview** → **User Limit**.
* **Give Green-bot Move Members** (recommended, it then joins even when the channel is full):

  1. Click the **gear icon** (Edit Channel) next to the voice channel.
  2. Open **Permissions** → **Advanced permissions**.
  3. Click the **+**, choose **Roles / Members**, then **Green-bot**.
  4. Enable **Move Members** (green check).
  5. Click **Save Changes**.

  To allow it on every voice channel at once: **Server Settings** → **Roles** → **Green-bot** → **Permissions** → enable **Move Members** (and **Connect**, **Speak**).

{% hint style="info" %}
Discord requires this permission to let a bot into a full channel. Without it, the bot can only join when a slot is free.
{% endhint %}

## 3. The permission is given but it still fails

A **channel-level override** beats the server-level role. If the channel (or its category) has a red cross ✗ on **Connect**, **Speak** or **Move Members** for Green-bot, for its role, or for **@everyone**, the bot is denied even though the role allows it.

1. Click the **gear icon** (Edit Channel) next to the voice channel → **Permissions**.
2. Look at **Green-bot** and **@everyone** in the list. Any red ✗ on **Connect**, **Speak** or **Move Members** is the problem.
3. Click that entry and switch the permission to the green check ✓ (Allow) for **Green-bot**. A grey slash `/` means "use the server default".
4. Check the **category** too: if the channel is **synced** with its category, edit the category's permissions (Edit Category → **Permissions**) or un-sync the channel first.
5. Click **Save Changes**, then try `/play` again.

{% hint style="info" %}
Still denied? Check the channel's list for any other role the bot has, and for a permission set on **Green-bot** itself (a member-level entry), then repeat step 3 there.
{% endhint %}

## Still not working?

Join our [support server](https://discord.gg/greenbot) and tell us the name of the voice channel and the exact message you got. A moderator will help.
