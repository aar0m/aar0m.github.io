---
layout: project
type: project
image: img/goatsandtigers/goats-and-tigers_wallpaper_centered.png
title: "Goats and Tigers"
date: 2024-01-14
published: true
labels:
  - Python
  - Automation
  - Database
summary: "A VIP X96 Project developed by our team that uses neural networks to infer optimal board game strategies."
---

<img class="img-fluid" src="../img/goatsandtigers/goats-and-tigers_wallpaper.png">

"Goats and Tigers" or _Huligutta_ is a turn-based game that pits two players against each other on a uniquely shaped map consisting of empty nodes. Similar to chess, each player takes control of a piece (Goat or Tiger) and must achieve a piece-specific win condition based on their available moveset. Three Tiger pieces exist on the board before the game starts and can be moved immediately, whereas 15 Goat pieces must be placed on the board before each individual piece can be moved. Both pieces can only move to adjacent nodes. Tigers win by **capturing** 6 Goats, a move where Tigers remove Goat pieces from play. Capturing is only possible when the Tiger is next to a Goat and the Goat has an empty space behind it. Goats win by **stalemating** all 3 Tigers. This is achieved by having Goats surround all 3 Tigers in a manner that prevents Tigers from making any movements or captures.

We use this game as a framework for developing a player model that can succesfully win as the Goat player. This is completed through the implementation of _Deep Neural Networks_ and _Reinforcement Learning_ (RL). Currently, we are attempting to increase the scope of this project by using available RL libraries and environments (i.e. OpenSpiel) to train player models for a Tiger player. I am a programmer for this project, responsible for refactoring the game (originally implemented in Python) so that it is compatible with the RL libraries and environments so new models can be trained.

This code simply instantiates the game and specifies the parameters required so it can interface with the OpenSpiel library.

```python
from open_spiel.python.observation import IIGObserverForPublicInfoGame
import pyspiel

_NUM_PLAYERS = 2
_NUM_ROWS = 5
_NUM_COLS = 6
_NUM_CELLS = _NUM_ROWS * _NUM_COLS
_GAME_TYPE = pyspiel.GameType(
    short_name="tigersandgoats",
    long_name="Python Goats and Tigers",
    dynamics=pyspiel.GameType.Dynamics.SEQUENTIAL,
    chance_mode=pyspiel.GameType.ChanceMode.DETERMINISTIC,
    information=pyspiel.GameType.Information.PERFECT_INFORMATION,
    utility=pyspiel.GameType.Utility.ZERO_SUM,
    reward_model=pyspiel.GameType.RewardModel.TERMINAL,
    max_num_players=_NUM_PLAYERS,
    min_num_players=_NUM_PLAYERS,
    provides_information_state_string=True,
    provides_information_state_tensor=False,
    provides_observation_string=True,
    provides_observation_tensor=True,
    parameter_specification={})
```

You can learn more at the [UH Vertically Integrated Projects (VIP) Website](https://manoa.hawaii.edu/uh-vip/project/asig/) and view a version of the [GitHub repository](https://github.com/nsanthan/tigersandgoats).