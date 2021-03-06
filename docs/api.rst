APIs
****

Simulation Config API
=====================

``reset(seed=False)``: 

- Reset the simulation
- Reset random seed if ``seed`` is set to ``True``


``set_random_seed(seed)``:

- Set seed of random generator to ``seed``
- Input format: int

``next_step()``:
- Simulate one step, a simulation step indicates one hour in the real world.


Data Access API
===============

``get_man_infection_state(manID)``:

- Args: manID - id for man
- Return: infection status of this man, ``1: susceptible``, ``2: pre-symptomatic``, ``3: symptomatic``, ``4: critical``, ``5: recovered``.


``get_man_intervention_state(manID)``:

- Args: manID - id for man
- Return: instervention status of this man, ``0: no such man id``,``1: without intervention``, ``2: confined``, ``3: quarantined``, ``4: isolated``, ``5: hospitalized``.




``get_region_visited_history(PoiID)``:

- Args: PoiID - id for the POI
- Return: a 2D list of the visited history of one POI. Each of the inner 1D list represents the history for one hour. [[manID1, manID2, manID3, ...], [manID7, manID8,]]


``get_man_visited_history(manID)``:

- Args: manID
- Return: a 1D list of the id of the POIs that he/she has visited. 
[poiID1, poiID2, ...]


``get_man_visited_history_with_p_infection(manID)``:

- Args: manID
- Return: a 2D list of the probabilities of geting infected (from acquantaince contacts and stranger contacts) in the POIs that he/she has visited. 
[[p_acq1, p_stranger1], [p_acq2, p_stranger2], ...]


``get_region_contained_man()``:

- Return: a dictionary with POI id as the key, and the list of manID who live in this POI as the value 

``get_region_infected_cnt(poiID)``:

- Args: poiID
- Return: an int representing the number of infected people in this POI


``get_life_count()``:

- Return the number of people not in hospital.

``get_infect_count()``:

- Return the number of infected people.


``get_hospitalize_count()``:

- Return the number of hospitalized people.

``get_isolate_count()``:

- Return the number of isolated people.

``get_quarantine_count()``:

- Return the number of quanrantined people.

``get_confine_count()``:

- Return the number of confined people.


``get_stranger_count()``

- Return the number of stranger contacts.

``get_acquaintance_count()``

- Return the number of acquaintance contacts.


``get_current_time()``:

- Get simulation time (in hour)
- Return a ``int``

``get_current_hour()``:

- Get simulation time (in hour of day)
- Return a ``int``

``get_current_day()``:

- Get simulation time (in day)
- Return a ``int``



Intervention API
===========

``set_man_isolate_days(days_to_isolate)``: 

- Args: days_to_isolate 
- a dictionary with manID as key and days for each person to be isolated as value.

``set_man_quarantine_days(days_to_quarantine)``:

- Args: days_to_quarantine 
- a dictionary with manID as key and days for each person to be quarantined as value.

``set_man_confine_days(days_to_confine)``:

- Args: days_to_confine - a dictionary with manID as key and days for each person to be confined as value.

``set_man_to_treat(if_treat)``

- Args: if_treat 
- a dictionary with manID as key and whether he/she is sent to be treated as value.



Other API
=========

``TBD``
