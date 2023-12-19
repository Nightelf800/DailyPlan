# VFDpeth 代码问题

network/volumetric_fusionnet.py



self.voxel_size[i] - 1为什么要减1

```python
voxel_unit_size: [1.0, 1.0, 1.5] # size of unit voxel in (m), [x, y, z]
voxel_size: [100, 100, 20] # num of voxels in each dimension. [x, y, z]
voxel_str_p: [-50.0, -50.0, -15.0] # voxel start point [x, y, z]
self.voxel_end_p = [self.voxel_str_p[i] + self.voxel_unit_size[i] * (self.voxel_size[i] - 1) for i in range(3)]
```



这是定义的投影的pixel图像大小

```python
# define grids in pixel space
self.img_h = self.height // (2 ** (self.fusion_level+1))
self.img_w = self.width // (2 ** (self.fusion_level+1))
self.num_pix = self.img_h * self.img_w
self.pixel_grid = self.create_pixel_grid(self.batch_size, self.img_h, self.img_w)
self.pixel_ones = torch.ones(self.batch_size, 1, self.proj_d_bins, self.num_pix)
```

