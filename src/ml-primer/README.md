# Machine Intelligence Primer

A structured, comprehensive primer on machine intelligence with full LaTeX support for mathematical notation.

## Structure

```
src/ml-primer/
├── index.html           # Main table of contents page
├── index.md             # Table of contents content (edit this!)
├── primer.css           # CSS Stuff
├── content/             # Individual chapter content
│   ├── linear-regression.html  # Chapter page
│   ├── linear-regression.md    # Chapter content (edit this!)
│   └── ...              # More chapters
├── images/              # Images
│   ├── somethingsomething.png  # Images
└── README.md            # This file
```

## How to Use

### 1. Edit the Table of Contents
- Modify `index.md` to update the main primer page
- Add/remove chapters and descriptions
- Update links to match your chapter filenames

### 2. Create New Chapters

**Step 1**: Create the markdown content
```bash
# Create a new chapter markdown file
touch src/ml-primer/content/your-chapter-name.md
```

**Step 2**: Create the corresponding HTML file
- Copy `content/what-is-ml.html` to `content/your-chapter-name.html`
- Update the `fetch('what-is-ml.md')` line to `fetch('your-chapter-name.md')`
- Update the page title

**Step 3**: Add to table of contents
- Edit `index.md` and add a link to your new chapter

### 3. Writing Content

#### Markdown Features
- **Headers**: `#`, `##`, `###`, `####`
- **Bold**: `**text**`
- **Italic**: `*text*`
- **Links**: `[text](url)`
- **Lists**: `-` for bullets, `1.` for numbers
- **Code**: \`inline code\` or \`\`\`code blocks\`\`\`

#### LaTeX Math
- **Inline math**: `$f(x) = x^2$`
- **Display math**: `$$\int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}$$`
- **Symbols**: `\alpha`, `\beta`, `\theta`, `\nabla`, `\sum`, `\int`
- **Fractions**: `\frac{numerator}{denominator}`
- **Sets**: `\mathcal{X}`, `\mathbb{R}`, `\in`, `\subseteq`

#### Example LaTeX
```latex
The loss function is:
$$L(\theta) = \frac{1}{n}\sum_{i=1}^{n} \ell(f_\theta(x_i), y_i)$$

where $\theta \in \mathbb{R}^d$ are the model parameters.
```

## IMAGE GUIDE

### Simple Image
```markdown
![Alt text](../images/filename.png)
```

### Image with Title
```markdown
![Linear Regression](../images/linear_regression_example.png "Line of best fit example")
```

### Centered Image
```markdown
<div class="center">

![Centered Image](../images/filename.png)

</div>
```

## Advanced Image Styling

### Small Images
```markdown
<img src="../images/filename.png" alt="Description" class="small">
```

### Large Images (can overflow container)
```markdown
<img src="../images/filename.png" alt="Description" class="large">
```

### Side-by-Side Images
```markdown
<div class="side-by-side">

![First Image](../images/image1.png)
![Second Image](../images/image2.png)

</div>
```

### Figure with Caption
```markdown
<div class="figure">

![Your Plot](../images/filename.png)

<div class="figure-caption">
Figure 1: This is a detailed caption explaining what the figure shows and why it's important.
</div>

</div>
```


## Interactive Plots (Advanced)

For interactive plots, you can embed HTML/JavaScript:

```html
<div id="my-plot"></div>
<script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
<script>
    var data = [{
        x: [1, 2, 3, 4],
        y: [10, 11, 12, 13],
        type: 'scatter'
    }];
    
    Plotly.newPlot('my-plot', data);
</script>
```

Command shift V to preview.

## Best Practices

### Image Quality
- **DPI**: Use 150-300 DPI for crisp images
- **Format**: PNG for plots, JPEG for photos
- **Size**: Keep files under 1MB when possible

## Troubleshooting

### Image Not Showing?
1. Check the file path is correct relative to the markdown file
2. Ensure the image file exists in the `images/` directory
3. Check file permissions and naming (case-sensitive on some systems)

### Image Too Large?
1. Add CSS class: `<img src="..." class="small">`
2. Or resize the source image
3. Or use `max-width` in inline styles

### Blurry Images?
1. Increase DPI when generating: `plt.savefig(..., dpi=300)`
2. Use PNG format for plots and diagrams
3. Ensure original resolution is high enough
