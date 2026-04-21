# `person.json` Specification

Every `person.json` file must begin and end with opening and closing square brackets, like this:
```
[

]
```

These delineate a JSON array. The entirety of a `person.json` file is one big JSON array.

The first entry of every `person.json` main array must be a string. It is strongly recommended that that string be the name of the person to whom the schedule belongs.

Because this is a JSON array, after every entry there must be a comma.

```
[
    "name_goes_here",
]
```

The second entry of every `person.json` file must be an array representing a schedule entry. The array must be formatted like this:

`[[hr, min], [hr, min], "weekday_string"]]`

That is, the array must contain an array, a second array, and then a string. The first array represents the start time of the event. The second array represents the end time of the event. The third string represents the day(s) on which the event occurs.

The first two arrays must be of length 2. The weekday string must be of length `1 <= Length <= 5`

The entries here labeled `hr` must be integers from 0 to 23 (representing the hours in a day). The entries labeled `min` must be integers from 0 to 59 (representing the minutes in an hour).

All `hr` entries *must be parsed as army time*. That is, 1 AM must be represented as `[1, 0]` while 1 PM must be represented as `[13, 0]`.

`"weekday_string"` must be a string containing any number of the following characters in any order: "MTWRF". No other characters are allowed in the weekday string, and the letters must be capitalized. No characters may be repeated. These letters represent the days of the week on which the listed event recurs. 

For example, to schedule an event which happens on Tuesday and Thursday from 11:15 AM to 2:05 PM, I would write the following schedule entry:

`[[11, 15], [14, 5], "TR"]`

The following is equally valid:

`[[11, 15], [14, 5], "RT"]`

However, the following is invalid, because an event cannot end before it starts:

`[[14, 5], [11, 15], "TR"]`


```
[
    "name_goes_here",
    [[hr, min], [hr, min], "weekday_string"]]
]
```

Any number of event entries may be entered after the first one, separated by commas as necessary.

```
[
    "name_goes_here",
    [[hr, min], [hr, min], "weekday_string"]],
    [[hr, min], [hr, min], "weekday_string"]],
    [[hr, min], [hr, min], "weekday_string"]],
    [[hr, min], [hr, min], "weekday_string"]],
    [[hr, min], [hr, min], "weekday_string"]]
]
```

Additionally, no spaces are required (though they are recommended for readability). The following is also valid:

`
["name_goes_here",[[hr, min], [hr, min], "weekday_string"]],[[hr, min], [hr, min],"weekday_string"]],[[hr, min], [hr, min], "weekday_string"]]]
`

Optionally, after weekday_string, the schedule entries may include a "comment" string. No software should assume that a comment will be present, and a comment should not be reflected in the output of a program which accepts `person.json` files.

For any further syntax questions, refer to [json.org](https://json.org)