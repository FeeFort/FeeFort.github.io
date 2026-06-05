---
layout: default
title: Bot Commands
---

# Bot Commands

## !help

### Usage

```
!help
```
Sends a message with a list of all available commands.

---

## !ask

### Usage

```
!ask [question]
```

Allows you to ask the AI a question.

---

## !balance

### Usage

```
!balance
```

Shows the current user balance. Coins are purchased using channel points.

---

## !pay

### Usage

```
!pay [@user] [amount]
```

Allows you to transfer coins to another chat participant.

---

## !blackjack

### Usage

```
!blackjack [bet]
```

Blackjack against the bot.

- Minimum bet: **100**
- Deck: `6, 7, 8, 9, 10, J, Q, K, A`
- `A` always counts as **11**
- `10`, `J`, `Q`, `K` count as **10**
- A regular two-card `21` is effectively the same as blackjack in this implementation
- Payouts:
  - dealer bust or normal higher-sum win returns **x2**
  - player blackjack returns **x5**
  - a push returns the stake

### Odds table

| Outcome | Chance | Notes |
|---|---:|---|
| Win with blackjack | 8.78% | `A + 10/J/Q/K` for the player, no dealer blackjack |
| Win by higher total | 33.10% | The player's total is higher than the dealer's |
| Win because the dealer busts | 1.22% | Dealer goes above 21, player is 21 or less |
| Push / stake returned | 13.79% | All ties, including both blackjack and both bust |
| Total win chance | 43.10% | All winning outcomes combined |

The code also has a separate `sum == 21` check, but with this deck it does not create a separate scenario, because any two-card `21` here is always blackjack.

---

## !casino

### Usage

```
!casino [bet]
```

Allows you to gamble coins in a casino.

### Odds table

| Emoji | Probability (V) | V (two emojis) | 1 in N | V (jackpot) | 1 in N | X |
|:------:|:---------------:|:--------------:|:----------:|:-----------:|:----------:|:-:|
| 7️⃣ | 0.1% | 0.0002997% | 333 667 | 0.0000001% | 1 000 000 000 | 1000 |
| 👑 | 1.0% | 0.0297% | 3 367 | 0.0001% | 1 000 000 | 500 |
| 💎 | 2.0% | 0.1176% | 850 | 0.0008% | 125 000 | 100 |
| 🍌 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍓 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍎 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍇 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍋 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍊 | 13.84% | 4.9511% | 20.2 | 0.2651% | 377 | 2 |
| 🍒 | 13.86% | 4.9642% | 20.1 | 0.2663% | 376 | 2 |

---

## !roulette

### Usage

```
!roulette [bet]
```

«Russian roulette» game.

- Payout: **x1.5**
- Win chance: **1 in 6** (~**16.7%**)

---

## !duel

### Usage

```
!duel [@user] [bet]
```

### Accept or decline a duel
```
!duel accept/decline
```

Challenges another chat participant to a duel.

- Winner takes double the bet
- Loser loses their bet
- Win chance: **50/50**

---

## !color

### Usage

```
!color [bet] [color EN]
```

Color roulette. You must guess the color.

- If correct → **x1.5 payout**
- Win chance for a specific color: **1 in 9** (~**11.1%**)

### Available colors

| Input (command) | Display (output) | Emoji | Probability | Multiplier |
|---|---|---|---:|---:|
| white | White | ⚪ | 11.1% | x1.5 |
| black | Black | ⚫ | 11.1% | x1.5 |
| red | Red | 🔴 | 11.1% | x1.5 |
| blue | Blue | 🔵 | 11.1% | x1.5 |
| orange | Orange | 🟠 | 11.1% | x1.5 |
| yellow | Yellow | 🟡 | 11.1% | x1.5 |
| green | Green | 🟢 | 11.1% | x1.5 |
| purple | Purple | 🟣 | 11.1% | x1.5 |
| brown | Brown | 🟤 | 11.1% | x1.5 |
