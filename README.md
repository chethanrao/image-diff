## ImageDiff

Tool allowing to simply (_and strictly_) compare two images. It checks for size and pixel by pixel equality. If required, an animated GIF image can be created with the diff output (GIF is a sequence of actual, expected and generated image with differences).

### Usage

```java
import static com.emichal.imagediff.ImageDiff.image;

    public void performSomeCoolTesting() throws IOException {

        // check only for equal dimensions
        assertThat(image(actual)
                .comparedTo(expected)
                .hasEqualDimensions());

        // check for equality and save output
        assertThat(image(actual)
                .comparedTo(expected)
                .withOutput(output)
                .isEqual());

        // check for equality within specified region
        assertThat(image(actual)
                .comparedTo(expected)
                .withinRectangle(start, end)
                .isEqual());
    }
```