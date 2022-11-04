# C - Sorting algorithms & Big O
This is a ALX Holberton School project on sorting algorithms in C language.

<p align="center">
<img src="https://s3.amazonaws.com/intranet-projects-files/holbertonschool-low_level_programming/248/willy-wonka.png" width="600" height="250" />
</p>

## Table of Contents
| `Files` | `Description` |
| --- | --- |
| [sort.h](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/sort.h) | Header file which contains all the function prototypes. | 
| [0-bubble_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/0-bubble_sort.c), [0-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/0-O) | A function that sorts an array of integers in ascending order using the Bubble sort algorithm. |
| [1-insertion_sort_list.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/1-insertion_sort_list.c), [1-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/1-O) | A function that sorts a doubly linked list of integers in ascending order using the Insertion sort algorithm. |
| [2-selection_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/2-selection_sort.c), [2-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/2-O) | A function that sorts an array of integers in ascending order using the Selection sort algorithm. |
| [3-quick_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/3-quick_sort.c), [3-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/3-O) | A function that sorts an array of integers in ascending order using the Quick sort algorithm. |
| [100-shell_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/100-shell_sort.c) | A function that sorts an array of integers in ascending order using the Shell sort algorithm, using the `Knuth sequence`. |
| [101-cocktail_sort_list.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/101-cocktail_sort_list.c), [101-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/101-O) | A function that sorts a doubly linked list of integers in ascending order using the [Cocktail shaker sort](https://alx-intranet.hbtn.io/rltoken/bwa4mHfUbbWTB8J2OIHvpA) algorithm. |
| [102-counting_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/102-counting_sort.c), [102-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/102-O) | A function that sorts an array of integers in ascending order using the Counting sort algorithm. |
| [103-merge_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/103-merge_sort.c), [103-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/103-O) | A function that sorts an array of integers in ascending order using the [Merge sort](https://alx-intranet.hbtn.io/rltoken/8sZ3nAhd_YLNzHCgNbbf8A) algorithm. |
| [104-heap_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/104-heap_sort.c), [104-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/104-O) | A function that sorts an array of integers in ascending order using the Heap sort algorithm. |
| [105-radix_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/105-radix_sort.c) | A function that sorts an array of integers in ascending order using the [Radix sort](https://alx-intranet.hbtn.io/rltoken/pBsj4j_AF_mJAgNZWmX3VQ) algorithm. |
| [106-bitonic_sort.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/106-bitonic_sort.c), [106-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/106-O) | A function that sorts an array of integers in ascending order using the [Bitonic sort](https://alx-intranet.hbtn.io/rltoken/N-bjAbxm5yr4DoeIDz5lLw) algorithm. |
| [107-quick_sort_hoare.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/107-quick_sort_hoare.c), [107-O](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/107-O) | A function that sorts an array of integers in ascending order using the [Quick sort](https://alx-intranet.hbtn.io/rltoken/_pBTrH0Xyo4BRmQn4CtnMg) algorithm. |
| [1000-sort_deck.c](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/1000-sort_deck.c), [deck.h](https://github.com/TosinISOGUN/sorting_algorithms/blob/main/deck.h) | A function that sorts a deck of cards. |

## Environment & Requirements
<img src="https://alx-apply.hbtn.io/brand_alx/share_image_2019.jpg" width="300" height="100" />

- Allowed editors: `vi`, `vim`, `emacs`
- Compiler;
  - Ubuntu 20.04 LTS using gcc.
  - Using the options `-Wall -Werror -Wextra -pedantic -std=gnu89`
- Coding style;
  - Betty Style.
- The use of global variables is not allowed.

## Data Structure and Functions
- For this project we are given the following `print_array`, and `print_list` functions:

```C
#include <stdlib.h>
#include <stdio.h>

/**
 * print_array - Prints an array of integers
 *
 * @array: The array to be printed
 * @size: Number of elements in @array
 */
void print_array(const int *array, size_t size)
{
    size_t i;

    i = 0;
    while (array && i < size)
    {
        if (i > 0)
            printf(", ");
        printf("%d", array[i]);
        ++i;
    }
    printf("\n");
}
```
```C
#include <stdio.h>
#include "sort.h"

/**
 * print_list - Prints a list of integers
 *
 * @list: The list to be printed
 */
void print_list(const listint_t *list)
{
    int i;

    i = 0;
    while (list)
    {
        if (i > 0)
            printf(", ");
        printf("%d", list->n);
        ++i;
        list = list->next;
    }
    printf("\n");
}
```
**Here's the data structure for doubly linked list:**
```C
/**
 * struct listint_s - Doubly linked list node
 *
 * @n: Integer stored in the node
 * @prev: Pointer to the previous element of the list
 * @next: Pointer to the next element of the list
 */
typedef struct listint_s
{
    const int n;
    struct listint_s *prev;
    struct listint_s *next;
} listint_t;
```

## Authors & Credits
- [Oluwatomisin ISOGUN](https://github.com/TosinISOGUN)
> Other collaborators are acknowledged within the project.
