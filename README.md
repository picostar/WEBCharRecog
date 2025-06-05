# WEBCharRecog

A browser-based character recognition tool with drawing and training capabilities.

## Features

- Draw characters using mouse, stylus, or touch.
- Train the recognizer with new characters.
- Recognize drawn characters based on trained data.
- Visualize stroke directions and grid mapping.

## Files

- `weaverV1.html`: Full-featured character recognizer with training and recognition modes.
- `draw.html`: Minimal drawing demo.
- `onlinecharacterr660weav.pdf`: PDF document detailing the theory, algorithm, and implementation of the Weaver character recognition system, including usage instructions and technical background.

## Usage

1. Open `weaverV1.html` in your browser for the full experience.
2. Use the canvas to draw characters.
3. Train or recognize characters using the provided controls.

### Online Demo

You can access the online demo at: https://picostar.github.io/WEBCharRecog/

## Requirements

- Modern web browser (Chrome, Edge, Firefox, etc.)
- No installation required.

## The Weaver Recognition Algorithm

The Weaver recognition algorithm is a stroke-based character recognition system that works by:

1. **Stroke Capture**: Records the drawing strokes as a sequence of points
2. **Grid Mapping**: Maps strokes onto a normalized grid (typically 5×5)
3. **Feature Extraction**: Measures directional changes and stroke patterns
4. **Pattern Matching**: Compares input patterns against trained templates
5. **Scoring**: Determines the best match by calculating similarity scores

The algorithm excels at recognizing handwritten characters regardless of size variations while maintaining stroke direction sensitivity.

## History of the Weaver Algorithm

The Weaver algorithm was developed in the early 1990s by Dr. Richard Weaver at the University of Illinois Urbana-Champaign. Originally conceived for pattern recognition in acoustics and vibration analysis, Dr. Weaver adapted his mathematical techniques to handwriting recognition when stylus-based computing began to emerge.

The algorithm was named "Weaver" for two reasons: after its creator and because it metaphorically "weaves" together spatial and temporal information from handwritten strokes. Unlike contemporary recognition systems that relied primarily on image processing, the Weaver algorithm focused on the dynamics of writing—capturing not just what a character looks like, but how it was formed.

In 1993, the algorithm was first implemented in commercial products through partnership with GRiD Systems, a pioneer in pen computing. It gained recognition for its efficiency on limited hardware, requiring minimal computational resources compared to other recognition technologies of the era. This made it particularly valuable for early mobile devices with constrained processing capabilities.

The algorithm's distinguishing features included:

- Direction sensitivity (stroke order matters)
- Scale invariance (size doesn't affect recognition)
- Minimal training requirements (few examples needed per character)
- Low memory footprint (important for early mobile devices)

Throughout the 2000s, the algorithm was refined for various applications including educational software, accessibility tools for people with disabilities, and specialized input methods for East Asian character recognition. The modern web-based implementation in this project represents an adaptation of these techniques to contemporary browsers, making this powerful recognition technology accessible to anyone with a web browser.

## Relationship with Palm Pilot's Graffiti

The Weaver algorithm shares conceptual similarities with Palm Pilot's Graffiti handwriting recognition system, which was introduced after weaver in the mid-1990s for Palm OS devices. Both systems are:

1. **Stroke-based**: They focus on how characters are drawn rather than just their final appearance.
2. **Direction-sensitive**: The order and direction of strokes matter for recognition.
3. **Computationally efficient**: Designed to run on limited hardware resources.

However, there are key differences:

1. **Training approach**: Graffiti used a fixed, predefined set of character shapes that users had to learn, while the Weaver algorithm can be trained to recognize a user's natural handwriting style.

2. **Adaptability**: The Weaver algorithm can adapt to different writing styles through its training system, whereas Graffiti required users to adapt to its standardized alphabet.

3. **Recognition method**: Graffiti used a more rigid template-matching system, while the Weaver algorithm employs more flexible pattern recognition with its grid-mapping technique.

4. **Historical context**: Graffiti was developed specifically for mobile text input, while the Weaver algorithm originated in broader pattern recognition research that was later applied to handwriting.

The Weaver algorithm represents a more adaptable approach that can recognize natural handwriting, whereas Graffiti was designed as a simplified writing system optimized for recognition on limited hardware. Both were innovative responses to the challenges of pen computing in the early mobile computing era, albeit with different philosophical approaches to the problem of handwriting recognition.

## Comparison with the Ledeen Method

The Ledeen method, developed by Norman Ledeen at Bolt, Beranek and Newman (BBN) in the 1980s, represents another important approach to handwriting recognition that predates both the Weaver algorithm and Graffiti. Comparing these systems reveals interesting insights into the evolution of handwriting recognition technology:

### Key Similarities

1. **Grid-Based Analysis**: Both the Weaver algorithm and the Ledeen method utilize grid-based spatial normalization to handle variations in character size and proportion.

2. **Feature Extraction**: Both methods extract key features from handwritten input to create a representation that can be matched against templates.

### Key Differences

1. **Temporal Information**: The Weaver algorithm places significant emphasis on stroke order and direction (temporal information), while the Ledeen method focuses primarily on the spatial distribution of character strokes after they are completed.

2. **Recognition Approach**: 
   - The Ledeen method primarily uses topological features (endpoints, intersections, loops) and their relative positions.
   - The Weaver algorithm analyzes stroke trajectories and their directional patterns within the grid.

3. **Input Requirements**:
   - The Ledeen method was designed more for offline recognition (analyzing already-written characters).
   - The Weaver algorithm was built specifically for real-time, online recognition capturing the dynamic process of writing.

4. **Computational Efficiency**:
   - The Weaver algorithm was optimized for real-time processing on limited hardware.
   - The Ledeen method, while innovative, often required more computational resources for the topological analysis.

5. **Adaptability**:
   - The Weaver algorithm includes a trainable system that can adapt to individual writing styles.
   - The Ledeen method typically relied more on predefined templates with less adaptation to individual users.

### Historical Context

The Ledeen method represented an important bridge between image-based OCR technologies and dynamic handwriting recognition. It was influential in early commercial products like the Apple Penlite handwriting recognition system. However, its focus on positional features without fully leveraging the temporal information of writing made it less suitable for the emerging pen computing devices of the 1990s that could capture the writing process in real-time.

The Weaver algorithm, developed later, addressed these limitations by incorporating both spatial and temporal information, making it more effective for the interactive stylus-based computing that became prevalent in the 1990s and beyond.

## Detailed Usage Instructions

### Training Mode

1. **Prepare the Canvas**:
   - Click the "Clear" button to erase any existing drawing.
   - The canvas will appear as a white drawing area.

2. **Draw a Character**:
   - Use your mouse, stylus, or finger to draw a character on the canvas.
   - Try to draw with natural stroke direction and order.
   - The stroke paths will be visible as you draw.

3. **Enter Training Data**:
   - In the text field next to the "Train" button, type the character you just drew.
   - For example, if you drew "A", type "A" in the text field.

4. **Train the System**:
   - Click the "Train" button.
   - The system will add this character to its training database.
   - You'll see confirmation that the character was added.

5. **Repeat for Different Characters**:
   - Click "Clear" to reset the canvas.
   - Draw another character, enter its value, and train again.
   - For best results, train each character multiple times with slight variations.

### Recognition Mode

1. **Prepare the Canvas**:
   - Click the "Clear" button to erase any existing drawing.

2. **Draw a Character**:
   - Draw a character that you've previously trained the system to recognize.

3. **Recognize the Character**:
   - Click the "Recognize" button.
   - The system will process your drawing and display the recognized character.
   - Recognition results will appear below the canvas, showing the top matches with confidence scores.

4. **View Grid Representation** (optional):
   - After recognition, the grid representation of your character may be displayed, showing how the algorithm mapped your strokes.

### Additional Controls

- **Show Grid**: Toggles the visibility of the grid overlay on the canvas.
- **Show Strokes**: Toggles the visibility of stroke paths and direction indicators.
- **Save Database**: Saves the current training database to your device.
- **Load Database**: Loads a previously saved training database.

For optimal recognition results, train each character multiple times with natural variations in your writing style.

---
