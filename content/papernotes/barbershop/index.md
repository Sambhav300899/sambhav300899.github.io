---
title: "Barbershop: GAN-based Image Compositing using Segmentation Masks"
date: 2024-06-28
draft: true
description: "Taking a look at the barbershop paper"
slug: "segment-anything"
tags: ["paper notes"]
---

They present a novel solution to image blending, in particular targetting hairstyle transfer, based on GAN-inversion. They propose - 

1. A novel latent space for image blending which is better at preserving detail and encoding spatial information
2. Porpose a new GAN-embedding algorithm which is able to slightly modify images to conform to a common segmentation mask.

Some of the challenges in hairtransfer are - 

1. Visual properties of different parts of an image are not independent of each other i.e - The visual qualities of hair are influenced by lighting, colors transmitted from the underlying face, clothing and background. 
2. the pose of the head can vary from image to image + the geometry of their hair + shadows. 
3. The occlusion of various parts of an image.

One of their key insights is that mixing high quality images where corresponding pixels hold the same semantic meaning, produces better images with less undesirable artifacts. Therefore, the introduce a semantic alignment step in the pipeline. 

They break down the hairstyle into two main attributes - 
1. Structure - The coarser features of the hair (the locks of hair)
2. Appearance - The finer details (such as hair color)

Their approach uses GAN-inversion. where they encode images into an FS latent space (F = structure tensor, S = Appearance code), the blending of styles takes place in a the latent space rather than compositting images.

Main contributions - 

1. FS latent space for image representation. Better for preserving details and capable of encoding spatial info.
2. New GAN-embedding algo for aligned embedding. The algorithm embeds an image to be similar to an input image + slightly modifies the image to conform to a new segmentation mask.
3. An image blending algo capable of blending multiple images encoded in their new latent space. 

They say 95% of users preferred their approach over SOTA.