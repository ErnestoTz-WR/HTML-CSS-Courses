# 2. Core concepts

## CSS Specifications and W3 publishing documentation process

Code labeled as:

- **Recommendation** is good to go
- **Candidate Recommendation or Proposed Recommendation**: still waiting for feedback and approval. It is okay to be implemented but it might have some updates or working progress.
- **Superseded Recommendation**: aspect that has been replaced.
- **Draft stages** still experimental and are not supported by all browsers.

## CSS Values and Units

**Length** can be defined on CSS by two types of units:

- Absolute: Fixed units, always the same size. No affected by values in related elements. Example: px, cm, mm, pt.
```CSS
    h1{
        padding: 10px 20px 10px 20px;
    }
```

- Relative: Relational sizing, not fixed. Dependent upon values declared in parent and ancestor elements. Example: em, rem, vw, vh.

```CSS
    h1{
        padding: 1.2rem 2.3rem 1.2rem 2.3rem;
    }
```

## Colours 

### RGB

`rgb()` this indicates rgb as a function it expects integer parameters between 0-255 or 0% - 100%.

`rgba()` - term used for red green blue alpha, where alpha indicated the opacity as a percentage.

```CSS
rgb(55,34,40) /*No alpha channel*/
rgba(55,34,40,0.5) /*50% opacity*/
rgba(55,34,40,1) /*100% opacity*/
```

### HSL

Defines colours by their hue, saturation and lightness 
