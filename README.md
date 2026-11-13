# Rank Steal SMP Addon (Bedrock 1.21+)

## Install
1. Open `Rank_Steal_SMP.mcaddon` with Minecraft Bedrock.
2. Activate **Rank Steal SMP - Behavior Pack** and **Rank Steal SMP - Resource Pack** in the world.
3. Enable **Cheats** and **Beta APIs / Script APIs** if your Bedrock version asks for them.
4. Join the world. The first 15 unique players receive random ranks. Later players are `[Unranked]`.

## Gameplay
- Rank #1 is the highest rank.
- Colored rank prefixes appear in player nametags: `[#1]Player`.
- A ranked player who kills a higher-ranked player (smaller rank number) swaps ranks with them.
- An unranked player who kills a ranked player takes that rank; the victim becomes unranked.
- Kills against lower/equal-ranked players do not change ranks.
- Rank assignments persist using world dynamic properties.

## Health values requested
Base health is 20 HP. Target totals:
#1 50, #2 48, #3 46, #4 44, #5 42, #6 40, #7 38, #8 36, #9 34, #10 32, #11 30, #12 28, #13 26, #14 24, #15 22; Unranked 20.
Maximum target is 50 HP (25 hearts).

### Bedrock health limitation
The vanilla Bedrock Health Boost effect increases maximum health in 4 HP steps. This pack rounds each target DOWN to the nearest supported step so it never exceeds the 50 HP cap. Therefore the in-game health bar may show the nearest lower 4-HP value rather than every exact table value. Exact per-rank 2-HP increments require a custom health implementation beyond the vanilla player health API.

## Script commands
- `/scriptevent rank:my` - show your rank.
- `/scriptevent rank:top` - show online leaderboard.
- `/scriptevent rank:reset` - reset saved ranks. First run `/tag <player> add rank_admin` as an operator; only tagged admins can reset the roster.

## Notes
This addon uses the stable `@minecraft/server` 1.13.0 module and requires Bedrock 1.21.0 or newer. Test in a copy of your world before using it on a live SMP.
