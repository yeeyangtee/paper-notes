# CCNet: Criss-Cross Attention for Semantic Segmentation

Main contribution seems to be reducing the computational load of non-local blocks.
This is targeting the need for global attention mechanisms in the semantic segmentation task. Previously this was done using nonlocal blocks that performed dense attention between all pixels in feature maps, leading to insane memory + computation requirements.

The main idea of this paper is a criss cross attention block. Basically each pixel attends to all the pixels in the same row and column, which is a num_pixels * (num_pixels in rows + columns) = (H x W) * (H + W -1) complexity operation. Compare this with the nonlocal dense attention which is (H x W)^2.

In order to fulfil the claim of global attention, authors simply stack up 2 of the criss cross modules. This allows any pixel to be able to attend to any pixel within the 2 criss cross steps. Can visualise this as you only need 2 operations in X,Y direction to go from any pixel A to any pixel B.

Simple idea, very good. [Code](https://github.com/speedinghzl/CCNet)
