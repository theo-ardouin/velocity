# Velocity

A simple script from a scrum master searching for its fragmented team's velocity.

_Disclaimer_: It has _not_ been designed with anything in mind but a quick and dirty script.

## Requirements

- python3.9+

## Installation

- Copy the `velocity` script anywhere from this repository
- Run it as needed
- _Profit_?

## Usage

### Create a sprint

To add a sprint velocity for a given week, we can type the following:

```
$ velocity create <week number> [-g <group name> <days> <points...> ...]
```

As an example, one can use:

```
$ velocity create 19 -g backend 6 8 -g frontend 2 12
```

It creates a velocity for the week `19` composed of 2 groups: `backend` and `frontend`.
The `backend` group did `8` points in `6` days and the `frontend` group did `12` points in `2` days.

You may specify the total points as a sum, like so:

```
$ velocity create 19 -g backend 6 5 1 2
```

In the example, the `backend` group completed `5 + 1 + 2` points in `6` days.

### Calculate a velocity

To calculate a velocity, we can use the following command:

```
$ velocity get <week number> -w <week count> [-g <group name> <days> ...]
```

As an example:

```
$ velocity get 19 -w 6 -g backend 10 -g frontend 8
backend 10 1.6
frontend 12 2
= 22
```

From the `19`th week of the year and `6` weeks prior, calculate the velocity for 2 groups, `backend` and `frontend`.
For each group, `backend` will work `10` days, and frontend will work `8`.

This command will output for each group the number of points and ratio of points per day.
It will also display the total of points estimated for all groups. (`22` in the example)

### Delete a sprint

To delete a sprint, just use the `delete` action as the following:

```
$ velocity delete <week number>
```
