# p system integer factorization

> You can visit our repository on Github: [CqNatural/p-system-integer-factorization](https://github.com/CqNatural/p-system-integer-factorization)

## about

This is a p system model implement based on UPSimulator for trying to solve integer factorization problem. The code for the relevant rules for our p system is included in the `.txt` file in `rules/`. We write it with the UPLanguage.

To run the example:

1. You should get the simulator from [quancs/UPSimulator](https://github.com/quancs/UPSimulator).
2. Read the `docs` folder in UPSimulator repository to learn how to use it.
3. Import the `rules/integer-factorization.txt` instance file in our repository into UPSimulator.
4. Init environment and wait for the result PATIENTLY.

## custom your calculate

Just modify two rules at the bottom of the source file. As `N=15` for an example:

```
// ...
Environment{
    Rule Er1 = k -> (k, in all), 1;
    Rule Er2 = DissolveAllCompute -> (DissolveAllCompute, in all), 1;
	Membrane Compute compute {
        Object a,d^2;    
        Object N^15;                        // `Object N^{{n}}` MEANS THE NUMBER N FOR FACTORIZATION. HERE N = 15.
        Rule CMr2 = v^15 -> (f^15,here), 2; // YOU ALSO NEED TO MODIFY THE `v^{{N}}` AND `f^{{N}}`.
	}
}
// ...
```

