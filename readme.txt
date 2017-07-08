# Intro to Parallel Programming

## Lesson1 - Color to Greyscale Conversion
formula for color to greyscale conversion:

I = .299f * R + .587f * G + .114f * B

## Lesson2 - gaussian_blur

 Here is an example of computing a blur, using a weighted average, for a single
 pixel in a small image.

 Array of weights:

  0.0  0.2  0.0
  0.2  0.2  0.2
  0.0  0.2  0.0

 Image (note that we align the array of weights to the center of the box):

    1  2  5  2  0  3
       -------
    3 |2  5  1| 6  0       0.0*2 + 0.2*5 + 0.0*1 +
      |       |
    4 |3  6  2| 1  4   ->  0.2*3 + 0.2*6 + 0.2*2 +   ->  3.2
      |       |
    0 |4  0  3| 4  2       0.0*4 + 0.2*0 + 0.0*3
       -------
    9  6  5  0  3  9

         (1)                         (2)                 (3)


## Lesson3 - HDR Tone-mapping

 input : [2 4 3 3 1 7 4 5 7 0 9 4 3 2]
  min / max / range: 0 / 9 / 9

  histo with 3 bins: [4 7 3]

  cdf : [4 11 14]


  Your task is to calculate this cumulative distribution by following these
  steps.