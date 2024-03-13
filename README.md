[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/IF3rQO50)
# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

On slide 34, the chances of selecting a good pivot is 1/2, because the chosen pivot has an equal probability of being the smallest. When we use the median of 3 pivot method, it will pick the first, middle and last
position of the section of the array. The median will pick the middle of the three, so unless all elements are equal the algorithm won't pick the smallest or largest element. To be considered a good pivot,
the pivot should create two partitions, one being at most 3n/4. With the median of three method, the three elements have a 1/2 chance to be a good pivot. Assuming the array is in a random order, the possible
permutations of picking the pivot would be as follows. S = smaller than good pivot, G = Good pivot, M = more than good pivot.

(SSS), (SSG), (SSM), (SGG), (SGM), (SGS), (SMS), (SMM), (SMG), (GGG), (GGS), (GGM), (GSM), (GMS), (GSS), (GMM), (GMG), (GSG), (MMM), (MMS), (MMG), (MSS), (MGG), (MSG), (MGS), (MSM), (MGM).

The median of three is value in between the others, so not the smallest or the largest. This doesn't depend on the order you pick it in, so our permutations are now:


1(SSS), 3(SSG), 3(SSM), 3(SGG), 6(SGM), 3(SMM), 1(GGG), 3(GGM), 3(GMM), 1(MMM). 

The probabilty of these permutations is also different. Only 1/4 of values will be smaller or greater than the middle half of good pivots. So G = 1/2, S = 1/4, and M = 1/4. They will 
also choose either a good(X) or bad pivot(Y). So the probability of these and efficiency of the chosen pivot are:

1*(SSS) = $\ (1/4)^3 $ = 1/64, Y
3*(SSG) = $\ (1/4) ^2 * 1/2$ = 1/32 = 2/64 x 3 = 6/64, Y
3*(SSM) = $\ (1/4)^3 $ = 1/64 x 3 = 3/64, Y
3*(SGG) = $\ (1/4) * (1/2)^2 $ = 1/16 = 4/64 x 3 = 12/64, X
6*(SGM) = $\ (1/4) ^2 * 1/2$ = 1/32 = 2/64 x 6 = 12/64, X
3*(SMM) = $\ (1/4)^3 $ = 1/64 x 3 = 3/64, Y
1*(GGG) = $\ (1/2)^3 $ = 1/8 = 8/64, X
3*(GGM) = $\ (1/4) * (1/2)^2 $ = 1/16 = 4/64 x 3 = 12/64, X
3*(GMM) = $\ (1/4) ^2 * 1/2$ = 1/32 = 2/64 x 3 = 6/64, Y
1*(MMM) = $\ (1/4)^3 $ = 1/64, Y

Good pivots = 44/64 = 11/16
Bad pivots = 20/64 = 5/16

So using the median of 3 chooses a good pivot 11 out of 16 times or about 69% of the time. This is better than the first element with the chance of 50%.
Using the median of the 3 method has a better chance of choosing a good pivot than the first element does.



