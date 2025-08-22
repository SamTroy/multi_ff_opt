# Multi FF Opt
A set of tools to help make decisions for Fantasy Premier League, Telegraph Fantasy Football, Dream Team, Cloud Fantasy Football, and Fanteam

Open the notebook in the `run` folder and run the cells to get started

## Settings guide

### Format settings

- `last_date`: final gameweek inputted as an integer, or the final date inputted as a string, to limit the solver horizon
- `transfer_cost`: number of points by which the solver will penalise a transfer
- `weekly_decay`: ratio by which EV of each match in the future will be discounted per week. Applied on a basis of real time passed
- `vicecap_weight`: incentive to having a strong vice-captain, as a fraction of that players expected points
- `price_change_value`: SDT only, incentive for the solver to sell players who are dropping in price and buy those who are rising, expressed in points per 1m of net value gained
- `use_team_json`: `true` or `false` whether to use a team uploaded to the `teams` folder, will overrule the other initial settings and will ignore if one is not found
- `initial_team`: list of fpl codes e.g. `['', '']` defining the players at the start of the solve
- `initial_itb`: money in millions available at the start of the solve
- `initial_ft`: number of free transfers available at the start of the solve
- `preseason`: `true` or `false` for custom constrainsts as required
- `total_pts_cutoff`: proportion of the maximum player horizon EV below which to remove players from the solver run
- `ppm_cutoff`: proportion of the maximum player horizon points per million below which to remove players from the solver run
- `smart_cutoff`: proportion of players to remove from the solver run by a custom value metric
- `exclusions`: list of fpl codes e.g. `['', '']` defining the players at to exclude from the team
- `keeps`: list of fpl codes e.g. `['', '']` defining the players at to keep in the team
- `sim_number`: number of simulations to perform when running the `sim_solve()` function
- `noise_magnitude`: quantity by which to scale magnitude of noise when applied, default 1
- `seed_val`: to use a predermined seed for the noise random number generator
- `settings_noise`: `true` or `false` whether or not noise will be applied to settings as well as player EV when solving with noise

### Meta settings
- `solver_type`: `highs` to use the highs solver
- `solver_path`: `null` or the absolute filepath in your computer directory to the `highs.exe`, with double backslashed
- `presolve`: `true` or `false` to run a time-saving step to the solve
- `use_cmd`: `true` or `false` to use `os.system` or `subprocess` for running solver, default is `false`
- `time_limit`: number of seconds before solve is aborted
- `delete_tmp`: `true` or `false` to delete the contents of the `tmp` folder when solve is completed

With thanks to [Sertalp](https://github.com/sertalpbilal) for solver expertise, and [Elevenify](https://www.elevenify.com/) for generously sharing team projections
