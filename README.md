# Goblin Mod
#### General Networking, Rendering, and Physics Framework for Unsharded 10,000+ Interacting MMOFPS Players
<hr>

#### News

October 24, 2023: Alpha release delayed as we focus on porting the G.O.B. (acronym remains a secret) engine to a pure, real-time path-tracing engine. Currently it is using a traditional Z-buffer rasterization. Preliminary results of real-time ray tracing shows faster performance than rasterization at the scale of rendering 6 million Stanford dragons. Mind-blowing stuff. The original rasterization prototype schedule still runs in parallel for use in testing.

#### Introduction

[![](./206376334.png)](https://www.youtube.com/watch?v=rTbKslUxKVU)

This project started as a feasibility study for a PlanetSide 3 for 10,000 concurrent players, for the sake of a Goblin Tribe April Fools' video (with a FrogMike related punchline).

We ended up implementing an entire Networking + Rendering + Physics framework as a general solution for 10,000+ MMOFPS games with no sharding.

No sharding is important because MMOs are often hyped as "X number of players!" but with sharding this is disingenuous at best and outright fraud at worst. For example, when PlanetSide 2 claimed the Guinness World Record for "Most players in an online FPS battle" at 1,158 players in 2015, the DX9 ForgeLight engine was only capable of rendering 200 players at a time. This means out of 1,158 players, only a maximum of 200 interact with each other. Amazon Games' New World is the same, where it was hyped to be a 10,000 player MMORPG, and ended up only delivering a "2,500 player MMORPG"--but even that is disingenuous, especially with the absurd "physical" sharding where players were scattered in an impossibly large continent that turned the game into a "Glorified Walking Simulator" as well as the aggressive player culling you see in towns and the unplayable 50vs50 wars. In New World's defense, if you add the monster AI you get a "player" count of 10,000; also the Amazon Games executive at the time forced them to build over an unoptimized engine. In terms of the N-size MMOFPS problem as primarily an upload bandwidth network problem and secondarily a rendering problem, dividing/sharding 1,000 players into 5 shards of 200 players each is simply converting an N-size MMOFPS problem into an N/[limit of your renderer or upload bandwidth] problem resulting in this "1,000 Player MMOFPS!" to be in actuality a collection of five 200 player-size MMOFPS, which is an entirely different, incomparable game altogether compared to experiencing 1,000 players interacting with each other.

Goblin Mod framework allows you to experience heshing 10,000 players at once. Or more, depending on your upload bandwidth.

This framework allows for custom servers for different network/rendering/physics options: client/server authoritative, ping limits, interpolation, tick rate, weapon balance, TTK, headshot multiplier, sharding, and so on. If a player doesn't like the available game modes, they can start their own custom server.

This repository is NOT for a PlanetSide 3 but for the general MMOFPS framework that makes such a game and others like it possible. A separate community, or much better, a studio the size of Amazon Games, should be better equipped at solving the game design and user experience problems of PlanetSide 1 and 2 outside of networking, rendering, and physics.

#### Major Alpha Milestones

The following major Alpha milestones were completed on August 24, 2023:

* Real-time (240 FPS at 1080p on a GTX 1070m test laptop) rendering of 10,000 high poly animating models (40K vertices each)
* 10Gbps worst-case upload bandwidth for unsharded real-time network updates of all 10,000 players sent to each player
* Real-time physics for all 10,000 models

Not only does completing these milestones guarantee that whatever happens to PlanetSide 2 it can be recreated as-is given a community effort to import 3D assets and animations, completing them also guarantees orders of magnitude faster rendering, physics, and server performance.

This repository was made private following completion of major Alpha milestones to protect Alpha release and is planned to be made fully open source again on Beta. Weekly builds under https://github.com/PlanetSideGoblinMod/GoblinModeDemo/tags were removed.

#### Alpha Release: Goblin Mode

Major Alpha milestones do not include a fun, playable game. The remaining tasks are not nearly as complex as the major milestones, but they are nonetheless time-intensive such as movement/physics tests, network tests, usability tests, and most important of all, fun tests.

Alpha Release is planned to test the worst-case game mode called Goblin Mode, which is the minimum "playable" physics for 10,000 unsharded concurrent players with a maximum 10Gbps server upload bandwidth. Goblin Mode as a default game mode is meant to attract and keep the highest amount of players possible. Since Goblin Tribe is a competitive gaming clan, there will be an alternate, competitive game mode with options for CS2-style "subticks" among other detailed customizations.

#### Goals

#### Acknowledgements and Dedication

This project is dedicated to Goblin Tribe including GOB competitive and ex-members, the PlanetSide staff who made this scale of MMOFPS possible (especially Don Neufeld), and all of our friends in the PlanetSide 2 community especially Recursion, FEFA, Saka, PREY, DPSO, CIK, TIDE, H00D, ZYZZ, MADE, RALI, and many others. This project is also especially dedicated to FrogMike, Therum, Beefy, and Zagszy.

This project would not have begun if SadRobot didn't oblige in participating in our "How Would We Design PlanetSide 3 If We Programmed In Goblin Mode?" seemingly-schizophrenic brainstorming sessions to come up with an "unapologetically self-indulgent, lazy, slovenly, or greedy, typically in a way that rejects social norms or expectations" worst-case solution called the Goblin Mode (meme) Architecture. Special thanks to Khorror's cracked 3D modeling skills. Much gratitude for Riesz, Encoder, and FatherTime for voices. Thanks to everyone who encouraged, supported, advised, tested, and critically examined the project: TJ, Blaxxen, Sobek, Khorror, SadRobot, Riesz, Encoder, LostArrow (Marauder), Atlia, PotatoBoiler, Chicken, Bazuki, NP_Eazy, BerkleianMegatrends, Spjalle, and GoblinRum. Infinite thanks to Goblin Tribe, especially FrogMike and Sobek, all the genius Goblin leadership, for letting the world witness one of the greatest underdog stories in history. Thanks to the Berkeley EECS community of cracked engineers for technical consultations, moral encouragement, and for offering the CSUA Minifridge for server hosting (lol).

This project is dedicated to the scarcest resource in a game of thousands with no direction: Leadership. Leadership provides the Guided User Experience that PlanetSide 2 should have had in the beginning, that all properly designed games should have as its primary concern.

Thanks for the patience rly sry about the delays lmao also fuku Calskey
