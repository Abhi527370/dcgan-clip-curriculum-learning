# Curriculum Learning for DCGAN using CLIP-based Difficulty Estimation

## Overview

This project investigates curriculum learning for image generation using DCGAN on CIFAR-100.

Images are ranked using CLIP image-text alignment scores.

High alignment → Easy samples

Low alignment → Hard samples

A cumulative curriculum is used:

Stage 1: B1

Stage 2: B1 + B2

Stage 3: B1 + B2 + B3

Stage 4: B1 + B2 + B3 + B4

Stage 5: B1 + B2 + B3 + B4 + B5

## Dataset

CIFAR-100

## Difficulty Estimation

CLIP ViT-B/32

Difficulty = - CLIP(Image, True Class Text)

## Results

| Stage | FID | IS |
|---------|---------|---------|
| Stage 1 | 225.81 | 2.42 |
| Stage 2 | 116.66 | 3.63 |
| Stage 3 | 56.64 | 5.57 |
| Stage 4 | 39.86 | 6.53 |
| Stage 5 | 37.10 | 7.03 |

## Requirements

pip install open_clip_torch torchmetrics scipy