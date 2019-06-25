# ImageTransformations.jl

## Introduction

Image Transformation is the process of changing the coordinate system of an image
by resizing, rotating, etc.
These operations have various applications, e.g, medical image registration.

## Installation

```julia
(v1.0) pkg> add ImageTransformations
```

## Key functions

The exported functions in this package include
* `restrict` for 2-fold down sampling
* `imresize` for arbitrary resizing
* `imrotate` for image rotation
* `warp` for general image warping, and related functions
  + `WarpedView`
  + `warpedview`
  + `InvWarpedView`
  + `invwarpedview`

These functions all have docstrings that give more details about their usage.

There are in-place version of many of the functions, e.g., `imresize!` etc.
    
## Example

```julia
using ImageTransformations, TestImages
img = testimage("mandrill")
img_small = imresize(img, round.(Int, size(img)./2))
img_big = imresize(img, size(img).*2)
```

todo: show results