![](https://github.com/4G0R4/giveaway/blob/main/sn-logo.png)
# Giveaway Picker

## Provably fair bitcoin giveaway picker

Simple tool to give more transparency and credibility to bitcoin giveaways, raffles, tombola, draws, ballots and similar on SN. It will help you randomly pick winners fairly. Now you can:

- Bulk register unlimited participants (one per line)
- Randomly pick max 21 winners
- Select future block number for the draw to be executed
- Get a sharable link to share results with all participants
- Have results easily verified
- Save and share the results in a unique URL


## How it works


As the `blockhash` is just a number, its last 6 digits is converted to `decimal` using this function:

`var decimal = parseInt(blockhash.slice(-6), 16);`

Now we have an integer (0 to 16777215) from the `blockhash`.

After dividing this `decimal` by the number of participants, we use the modulo operator (`%`) to get the division remainder becomes the `index_number`.

This `index_number` is applied in the participants list, to get the position of the winner.

`var index_number = decimal % competitors.length;
var winner = competitors[index_number];`

For additional winners, the past winners are removed from the list and one more digit is added from the `blockhash`. A maximum 21 was added to avoid working with big numbers.


`if` you find this tool useful, refer to it in your upcoming giveaways and raffles, or zap some sats via <a href="https://coinos.io/pay/AGORA" target="_blank">lightning</a> or onchain `bc1qwcyfx0mfgxxuuf6yf2f04egjhh2xcgw8t2egf0`

