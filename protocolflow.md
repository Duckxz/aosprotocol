This document describes the general flow of the protocol,
 S is server, C is (all) client(s) and
 \* means all clients including self

# Map transfer
```
MapStart (S) -> C
MapChunk (S) -> C (sent until all chunks sent, chunks are 1024*1024 bytes)
ExistingPlayer (S) -> C (sends one for each connected or connecting(?) players)
StateData (S) -> C
```

# Respawn
```
CreatePlayer (S) -> C*
```

# Team change
```
ChangeTeam (C) -> S
KillAction (S) -> C*
```

# Weapon Change
```
ChangeWeapon (C) -> S
KillAction (S) -> C*
```

# After StateData
The StateData packet marks the end of the map and player transfer meaning it can be any of the other packets (mostly inputs and WorldUpdate)
