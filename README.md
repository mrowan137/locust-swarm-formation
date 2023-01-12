# Locust swarm formation
Computational model of locust swarm formation, implemented in
[NetLogo](https://ccl.northwestern.edu/netlogo/) (v4.1.2). The model can be used
to explore the notion of 'critical density', and how that affects swarm
formation.

<p align="center">
  <img src="https://github.com/mrowan137/locust-swarm-formation/blob/main/docs/demo/locust_swarm_formation_demo.gif">
</p>


## Description

The model loosely incorporates elements of the
[SIR (susceptible-infectious-removed) model](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model).
Grasshoppers are treated as 'susceptible', capable of turning into locusts.
A grasshopper can be 'infected' (i.e., turn into a locust) by making contact
with a sufficient number of other grasshoppers & locusts within a prescribed
window of time (the criterion is motivated by the idea that
[overcrowding induces swarm behavior](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3420939/)).
A locust is treated as 'removed', in the sense that once it
turns into a locust, it remains a locust (i.e., it could not be 'infected'
again).

The model also incorporates the notion of
[flocking](https://en.wikipedia.org/wiki/Flocking_(behavior)).
A grasshopper is assumed to wander randomly, whereas after turning into a locust,
it follows flocking/swarming behavior.

Model assumptions:
* only solitary (grasshopper) and gregarious (locust) members
* population is fixed
* members cannot escape world boundaries
* solitary can become gregarious
* gregarious remain gregarious
* grasshopper wanders randomly
* locust adopts swarming behavior

Model parameters:
* `population`: number of members in the grasshopper-locust population (all are
  initialized as grasshoppers)
* `locust-mobility`: distance a locust moves per cycle
* `vision`: distance around a locust within which neighbors are considered as
  swarm mates
* `minimum-separation`: distance below which a locust will separate from its
  nearest neighbor, and above which it aligns to the average swarm heading
* `max-align-turn`: maximum turn angle allowed by a locust aligning to the
  average swarm heading
* `max-cohere-turn`: maximum turn angle allowed by a locust cohering to the
  average swarm heading
* `max-separate-turn`: maximum turn angle allowed by a locust separating from
  its nearest neighbor


## Author

Michael E. Rowan — [mrowan137](https://github.com/mrowan137) — [michael@mrowan137.dev](mailto:michael@mrowan137.dev).


## License

[MIT License](https://github.com/mrowan137/locust-swarm-formation/blob/main/LICENSE).


## Acknowledgments
* The model is a modification of
[Uri Wilensky's flocking model](http://modelingcommons.org/browse/one_model/1404#model_tabs_browse_info),
which mimics e.g. the flocking of birds or fish.


## References
* [NetLogo](https://ccl.northwestern.edu/netlogo/)
* [Uri Wilensky's flocking model](http://modelingcommons.org/browse/one_model/1404#model_tabs_browse_procedures)
* [SIR model](https://en.wikipedia.org/wiki/Compartmental_models_in_epidemiology#The_SIR_model)
* [Locust Dynamics: Behavioral Phase Change and Swarming](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3420939/)
