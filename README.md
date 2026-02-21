# rate-cat-photo-background

Evaluates how well the background of a cat photograph stays out of the way. This function looks past the cat and examines everything else in the frame — the surfaces, objects, lighting, patterns, and surrounding environment — to determine whether that space defers to the cat as the clear visual subject or competes with it for the viewer's attention.

## Input

The function accepts a single input:

| Field | Type | Required | Description |
|---|---|---|---|
| `cat_photograph` | image | Yes | A photograph containing a cat as the intended subject. |

The photograph should contain a cat. The function does not evaluate the cat itself — its pose, expression, breed, or beauty are irrelevant. The entire evaluation is directed at the space surrounding the cat.

## Output

A scalar score between **0** and **1**.

- **Scores near 1.0** indicate a background that recedes gracefully. The cat is the unambiguous subject, and nothing in the surrounding environment pulls the viewer's eye away.
- **Scores near 0.5** indicate a background with moderate issues — some competing elements, mild clutter, or occasional tonal disruptions that partially distract from the cat without overwhelming it.
- **Scores near 0.0** indicate a background that actively competes with the cat. The viewer's attention is fragmented by clutter, competing focal points, or tonal disharmony, and the cat struggles to stand out as the subject.

## What It Evaluates

The score is derived from three qualities, each capturing a different dimension of background deference:

### 1. Visual Subordination

Does every element in the background accept a lower rank than the cat in the visual hierarchy? This quality checks whether any individual element — a bright object, a glowing screen, another animal, a person, vivid signage — surges forward to rival the cat in visual prominence. A subordinate background does not require emptiness. A richly detailed garden in soft bokeh, a furnished room with muted tones, or a plain wall can all be fully subordinate. What matters is that nothing outranks the cat.

**Scores well:** The cat is the most visually commanding presence. Background elements are present but quieter — softer, dimmer, less sharp, less saturated.

**Scores poorly:** A bright red object on a shelf, a television glowing with vivid color, another animal staring into the camera, or any element that demands its own attention and breaks the visual hierarchy.

### 2. Attentional Cohesion

Does the background allow the viewer's gaze to settle on the cat, or does it scatter attention across the frame? Where visual subordination looks for individual competitors, attentional cohesion evaluates the collective effect of everything behind the cat. Even when no single element dominates, an accumulation of many small objects, busy patterns, or varied textures can create visual noise that keeps the eye restless.

**Scores well:** The background feels like atmosphere — soft textures, uniform surfaces, muted tones, or gently blurred elements that give the gaze nowhere to wander. The eye lands on the cat and stays.

**Scores poorly:** Cluttered countertops with scattered objects, wildly patterned rugs, densely packed bookshelves, or any environment where the collective busyness makes the cat feel like one item among many rather than the clear subject.

### 3. Tonal Harmony

Do the colors, brightness, and contrast across the background exist in peaceful relationship with the cat and with each other? This quality evaluates the tonal fabric of the image. A tonally harmonious background allows even detailed or complex scenes to score well — a lush garden with complementary greens and soft, dappled light can be beautiful and non-distracting. What matters is that the palette feels unified and the lighting feels cohesive.

**Scores well:** Colors complement each other, light falls evenly or graduates softly, and the cat sits naturally within a unified visual world. The cat is tonally distinct from its surroundings without harsh separation.

**Scores poorly:** Harsh shadows cutting across surfaces, blown-out windows against dark interiors, objects in clashing saturated colors, or insufficient tonal separation causing the cat to merge into the background and lose definition.

## Use Cases

- **Photo curation and selection.** When choosing the best shot from a series of similar cat photographs, this function ranks images by how well the background serves the subject — surfacing the cleanest, quietest compositions automatically.

- **Social media optimization.** Cat photographs with clean, deferential backgrounds read instantly in a fast-scrolling feed. This function helps identify which images will make the strongest first impression by ensuring the cat is immediately and unambiguously the subject.

- **Professional and editorial photography.** Pet photographers, animal shelter adoption listings, and brands featuring cats in marketing materials can use this function to systematically filter for images where the cat reads as the clear subject with no visual competition.

- **Photographer feedback and education.** By scoring the background independently from the cat, this function helps photographers develop awareness of the space behind their subject — learning to see not just the cat they're capturing, but the stage they're placing it on.

## Philosophy

This function is built on a single belief: a great cat photograph is one where the cat does not have to compete. The background's job is not to be interesting or to tell its own story. It is to recede — gracefully, quietly, harmoniously — so that the cat can be fully and immediately seen. Visual subordination, attentional cohesion, and tonal harmony together define what it means for a background to defer, and that deference is the standard against which every score is measured.
