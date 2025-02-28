# TD1

## Exercice : Affichage d'un tableau à une ou deux dimension

### Soit $tab une variable qui sert à afficher la table de multiplication par 7, pour les valeurs de 1 à 10.

**1. Déclarer puis initialiser la variable $tab:**

```php
<?php

	// create a function that returns the multiplication table of a number
	function fill_table($number)
	{
		$index = 1;
		while ($index < 11)
		{
			$table[$index] = $index * $number;
			$index++;
		}
		return $table;
	}

	// initialize the $tab with the multiplication table of seven (7)
	$tab = fill_table(7);

?>
```

**2. Tester l'appel de la fonction var_dump () et print_r () avec comme argument $tab. Discuter leur fonctionnement.**

```php
<?php

	var_dump($tab);
	/*
	output of var_dump() is :
	array(10) {
	  [1]=>
	  int(7)
	  [2]=>
	  int(14)
	  [3]=>
	  int(21)
	  [4]=>
	  int(28)
	  [5]=>
	  int(35)
	  [6]=>
	  int(42)
	  [7]=>
	  int(49)
	  [8]=>
	  int(56)
	  [9]=>
	  int(63)
	  [10]=>
	  int(70)
	}
	*/
	print_r($tab);
	/*
	output of print_r() is :
	Array
	(
		[1] => 7
		[2] => 14
		[3] => 21
		[4] => 28
		[5] => 35
		[6] => 42
		[7] => 49
		[8] => 56
		[9] => 63
		[10] => 70
	)
*/

?>
```
We notice that the var_dump() get many informations from the variable such as (array size, index, type, value), but it's a little bit hard to read.
While the print_r() function which I consider means 'print_readable' prints the basic informations that you may need to see (index => value), so it's easy to read and manipulate.


**3. A l'aide des boucles (for, while, foreach, ... ), essayer d'obtenir les mêmes résultats.**

```php

	$index = 0;
	echo "Array\n(\n";
	while ($index < 11)
	{
		echo "    [$index] => ";
		var_dump($tab[$index]);
		$index++;
	}
	echo ")\n";

	// I couldn't find a way to NOT print the type while calling the vat_dump
	/**
	 * @var_dump()
	 *Array
	 *(
	 *    [0] => int(0)
	 *    [1] => int(7)
	 *    [2] => int(14)
	 *    [3] => int(21)
	 *    [4] => int(28)
	 *    [5] => int(35)
	 *    [6] => int(42)
	 *    [7] => int(49)
	 *    [8] => int(56)
	 *    [9] => int(63)
	 *    [10] => int(70)
	 *)
	 * /
```

***4. Ecrire un script capable de rendre l'affichage de la table plus lisible aux internautes.***

This is readable using print_r ! what does the question actually means ?



## Exercice : Compter le nombre de valeurs d’un tableau multi-dimension

### Soit le tableau suivant :
```php
	$t=array ("Bonjour", "chers étudiants", array("10","10","2024"), 2024,
array("M2I","MQL"));
```
***1. S'agit-t-il d'un tableau à une ou à deux dimension ?***

we have the array $t like this:
```bash
Array
(
	[0] => String(Bonjour)
	[1] => String(chers étudiants)
	[2] => Array (
			[0] => int(10)
			[1] => int(10)
			[2] => int(2024)
		)
	[3] => int(2024)
	[4] => Array (
			[0] => String(M2I)
			[1] => String(MQL)
		)
)
```
To answer the question we need to know what a 2D array is?
Basically an array is sequence of data stored in one memory block under one variable name.
So a 2D array is sequence of data each element contains more that one.
So I noticed in the given example, that the element [2] and [4] of our array is contains multiple elements (also an array).
That's why we can call it a 2D array. and we can use it as $t[i][j].
On the other hand if we tried to access the element $t[1][*] we will have a problem !

In summary this is really confusing me now!
But from my prespective there is two logical explanation:
	1. It's a 2D array because it contains at least one or more Array inside.
	2. It's not a 2D arrauy because a 2D array should have all the second elemeent accessable.


***2. En utilisant la fonction count (), comptez le nombre d'élément de la table. Discutez le résultat obtenu.***

```php
	printf("\ncounter: %d\n", count($tab));
```
count($array) is function that returns the size of the given array.
it parameter should be nothing but an array, and she doesn't accept null as a arg.

***3. Proposer un script permettant de compter le nombre d'élément de ce tableau.***

I will write a simple function that counts the Array's lenght:
```php
	function get_lenght($array)
	{
		$counter = 0;
		foreach ($array as $value)
			$counter++;
		return $counter;
	}
```

## Exercice : Manipulation des tables

```php
	$tab= array(10,20,20,30);
	$nb=array_unshift($tab,50,40);	//add to the beginning of the array
	$newnb=array_push($tab,70,20);	//add to the end of the array
	$suppr= array_pop($tab);		//pop an element from the end of the array
	$suppr= array_shift($tab);		//pop an element from the beginning of the array
	unset($tab[4]);					// pop the exact element with it index
	$tab = array_unique($tab);		// remove duplicated elements from an array
```

## 
