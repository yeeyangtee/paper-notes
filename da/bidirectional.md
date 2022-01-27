

### Forward direction, translation-to-segmentation (T2S)
- self supervised approach.
- segmentation is trained on both synthetic and real data, real data no labels
- use prediction on real data as pseudo label (with confidence threshold)
- This self supervised is simply the same as semi-sup methods doing psuedo label.

### Backward direction, segmentation to translation (S2T)
- translation module is updated by segmentation model using a perceptual loss
- 