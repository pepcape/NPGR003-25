# Task 02-ImagePalette
Your task is to design an algorithm that automatically computes a representative
color palette from an input raster image. The inspiration for this assignment
is a project [Cinema Palettes](https://www.facebook.com/cinemapalettes).

Your algorithm should analyze the input image and provide 3 to 10 characteristic
colors. If the image has a smaller number of hues (unique colors), you can output
less number of colors (minimum palette size is 1).

* Your task is to write a **C# command-line** program which reads an input image
  and prints down the palette in RGB
* Use simple text output format: three numbers on a line, one line per color
  * alternative output formats (PNG image and SVG image) will be demonstrated
	in the lab. They will be included in a pilot project here.
* One command line argument defines the **input file name**, another the **desired
  number of colors**, for example
```bash
 > imagepalette -i "input.png" -c 10
```
* For visual output formats include a `-o` option, see examples
```bash
 > imagepalette -i "input.png" -c 10 -o "palette.png"
 > imagepalette -i "input.png" -c 10 -o "palette.svg"
```
* You may not meet the required number of colors if you have serious reasons
  (which you must explain). The colour-poor image is one of the reasons you
  don't need to explain.

## Notes
You should use `.NET 8` which is available for all platforms now.

### Image library
Using of a simple image processing library is recommended. My option would
be [SixLabors.ImageSharp](https://www.nuget.org/packages/SixLabors.ImageSharp/).

### Command-line parsing
For the parsing of command-line arguments I'd recommend
[CommandLineParser](https://www.nuget.org/packages/CommandLineParser/).

### More libraries
When you use an AI wizard, it may suggest a numerical or statistical library.
You can use it, but do it properly through the [NuGet system](https://www.nuget.org/).

## Ideas to consider
* Play with other color spaces: HSV, CIE Lab*, etc.
* **Clustering** (do your own research!)
  * other color metrics
  * cluster post-processing
* **Color quantization** (do your own research!)

# Your solution
Please place your solution in a separate [solutions](solutions/README.md)
directory in the repository. You'll find short instructions there.

# Launch date
**Thursday 17 October 2025**
(Don't work on the solution before this date)

# Deadline
See the shared [point table](https://docs.google.com/spreadsheets/d/17XuX5tgvh_E0u17Y4BXtQK-qVt1qnr9zAXVHGkYrNWs/edit?usp=sharing).

# Credit points
**Basic solution: 8 points**
* input file and number of colors in command line arguments
* must not crash under any circumstances
* text palette output to `stdout`
* at least one of the "visual" outputs (SVG or PNG) - the `-o` argument
* reasonable palette for reasonable input images

**Bonus points: up to 7 more points**
* quality of output palette
* handling of difficult images
* output colors are pleasantly sorted

## Use of AI assistant
Using an AI assistant is recommended! But you have to be very critical and
test all its suggestions thoroughly. Especially test singular cases (one
pixel input image, single color image, etc.).

# Pilot version
We have included a pilot version of the project, just showing how the SVG
output can be done in C#. Only the `-o` command line argument is parsed, if
present, the SVG output is generated, otherwise a textual CSV output to `stdout`
is used.

The SVG generating code was generated with the help of `ChatGPT`. A couple
of fixes were done manually, the overall experience can be classified as "good".
The conversation is archived [here](https://chat.openai.com/share/c0bd824d-71e7-403d-a2a2-e418d4f16435).

# Input images
You can use following images for testing.

[Red stop sign](https://unsplash.com/photos/a-snow-covered-street-with-a-red-stop-sign-Ow3ycF_ZYI4)
[Orange windows](https://unsplash.com/photos/z9hvkSDWMIM)
[Pool](https://unsplash.com/photos/c4Eh-VZcWoc)
[Cat](https://unsplash.com/photos/7xsBS4vFR-g)
[Sunset, golden hour](https://unsplash.com/photos/WY_z540lzlU)
[NYC busy street](https://unsplash.com/photos/esPP01NpBfY)
[Narrow road](https://unsplash.com/photos/nTTh5UXkHp8)
[Fruits, many colors](https://unsplash.com/photos/ihP15orhXT4)

# Example
See the [Cinema Palettes page](https://www.facebook.com/cinemapalettes) for many examples.
Most are good enough (but input images are quite easy to process)...
