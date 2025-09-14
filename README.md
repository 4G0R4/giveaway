![](https://github.com/4G0R4/giveaway/blob/main/sn-logo.png)
# Giveaway Picker

## Provably fair bitcoin giveaway picker

A simple tool to give more transparency and credibility to bitcoin giveaways, raffles, tombolas, draws, and similar. It will simply help you randomly pick winners fairly. 

## How to use
1. Bulk register unlimited participants (one per line)
2. Randomly pick number of winners (max 210)
3. Select future block number for the draw to be executed
4. Get a sharable link to share results with all participants
5. Have results easily verified, simply hit "Submit" start the verification
6. Save and share the results in a unique URL

Repo: https://github.com/4G0R4/giveaway/
Demo: https://4G0R4.github.io/giveaway/
Try:
- Go to [this link](https://4g0r4.github.io/giveaway?U2FsdGVkX1+ylI2QBalBrjRbaEEXRJ9aM7AHGQ4JCOmpzBNk3Ltz/qHpfbBeIoO6WhLhcTtjeiR6SG7gO19UO4I/YJ1DyNs8vTjSFG4zU7msOKjK6t6jihpH/47wbBo+ZRDwZsg59rThVNa+K9Ew9G8Dhi6c7Kh4Y/w0ToaJHdGou7wqbx0DVtQqMY2pFiZT+7RpUkpS0FuwS6r4PFb5ET/cGjjERVZbJPkzCOrK14pk3JVBtF/wUtq4dXLGbi8dab7sQZ5uIzVcf3m6KpaXCPeWouUwWw4DbPAKLx9Di1MWbd7UX0F05/jxzl+dW7XKH5SMQS6HPesVUUzDxGzfqNCSvtSHPNtxFmb4i40R77f7L21vIrLe5LL9LEp4wiDwoK7n/N94yF/fhUAb5xEFp3iBY7N1/8ec13bpkX+RvEgrrgKJx/K21ZW1yIyeEhPnyGy1Ai0k5TGS713b/1CHRzgpSfXQyXaJkT5ZW5I6wjdjrRLa6i73DVz5ZQJlg5yHolRmEFZxXsGH0uBNoWUktQUqwzrAdFK4lYTKvqhA7j9uVKoaXdOOTy/UX8j7iX6ASxh/JzYN67ha11ZFhKieKQ==)
- Click **Submit** button
- View who are the 3 picked random stackers from today [top](https://stacker.news/top/stackers/custom?from=1757769019072&to=1757855419072) <sub>excluding hiding stacker</sub>

## How it works


As the `blockhash` is just a number, its last 6 digits is converted to `decimal` using this function:

```
var decimal = parseInt(blockhash.slice(-6), 16);
```

Now we have an integer (0 to 16777215) from the `blockhash`.

After dividing this `decimal` by the number of participants, we use the modulo operator (`%`) to get the division remainder becomes the `index_number`.

This `index_number` is applied in the participants list, to get the position of the winner.

```
var index_number = decimal % participants.length;
var winner = participants[index_number];
```

For additional winners, the past winners are removed from the list and one more digit is added from the `blockhash`. A maximum 210 was added to avoid working with big numbers.

- - - 

`if` you find this tool useful, refer to it in your upcoming giveaways and raffles, or zap some sats via <a href="https://coinos.io/pay/AGORA" target="_blank">lightning</a> or onchain `bc1qwcyfx0mfgxxuuf6yf2f04egjhh2xcgw8t2egf0`

