## Provably fair bitcoin giveaway picker

Simple tool to give more transparency and credibility to bitcoin giveaways on SN, since sin some cases, zaprank is not a good metric, and with many participants it's hard to randomly pich one (or many) winner fairly. Now you can:

- Have results easily verified.

- Save and share the results in a unique URL.


## How it works


As the `blockhash` is just a number, its last 6 digits is converted to `decimal` using this function:

`var decimal = parseInt(blockhash.slice(-6), 16);`

Now we have an integer (0 to 16777215) from the `blockhash`.

After dividing this `decimal` by the number of participants, we use the modulo operator (`%`) to get the division remainder becomes the `index_number`.

This `index_number` is applied in the participants list, to get the position of the winner.

`var index_number = decimal % competitors.length;
var winner = competitors[index_number];`

For additional winners, the past winners are removed from the list and one more digit is added from the `blockhash`. A maximum 30 was added to avoid working with big numbers.


If you find this useful  , please refer this tool in upcoming giveaways
