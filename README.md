# Debugging in Representation Learning

## Framework Issues

### GELU Implementation
- **Error**: `AttributeError: module 'torch.nn' has no attribute 'GELU'`
- **Reference**: [module 'torch.nn' has no attribute 'GELU' · Issue #2510 · facebookresearch/fairseq](https://github.com/facebookresearch/fairseq/issues/2510)
- **Solution**: This error occurs when using an older version of PyTorch which lacks the GELU (Gaussian Error Linear Unit) activation function. Upgrade PyTorch to a version that includes it.

## Dataset Handling

### MSR-Action3D and Synthia 4D
- **Reference**: For MSR-Action3D and Synthia 4D datasets, refer to the [MeteorNet work](https://github.com/facebookresearch/fairseq/issues/2510).

### NTU Dataset
- **Note**: The datasets are large, refer to the 3DV work or their preprocessing scripts.

### 4D Semantic Segmentation
- **Issue**: Handling long sequence point cloud videos
- **Reference**: [4D semantic segmentation on Synthia Dataset model code · Issue #4 · hehefan/P4Transformer](https://github.com/hehefan/P4Transformer/issues/4)

### NTURGBD60 Labels (Chinese)
- **List of Actions**:
* A1. 喝水。
* A2. 吃饭/吃零食。
* A3. 刷牙。
* A4. 梳理头发。
* A5. 手里东西掉落。
* A6. 拾起。
* A7. 扔东西。
* A8. 坐下。
* A9. 站立（从坐姿）。
* A10. 鼓掌。
* A11. 拿起书，看书或读书。
* A12. 拿起小本本上记东西。
* A13. 把小本本撕碎。
* A14. 穿外套
* A15. 脱掉外套。
* A16. 穿鞋。
* A17. 脱鞋。
* A18. 戴上眼镜。
* A19. 摘下眼镜。
* A20. 戴上帽子。
* A21. 脱下帽子。
* A22. Yeh欢呼。
* A23. 挥手。
* A24. 用脚踢东西。
* A25. 从口袋掏东西。
* A26. 跳（一只脚跳）。
* A27. 跳起来。
* A28. 拨打电话/接听电话。
* A29. 玩手机/平板电脑。
* A30. 在笔记本键盘上敲击。
* A31. 用手指指着某个东西。
* A32. 举起手机自拍。
* A33. 看手表时间。
* A34. 两只手一起搓手。
* A35. 点头/鞠躬。
* A36. 摇头。
* A37. 擦脸。
* A38. 敬礼。
* A39. 将手掌放在一起，祈祷。
* A40. 双手交叉在前面（例如停下来）。
* A41. 打喷嚏/咳嗽。
* A42. 摇摇晃晃地走。
* A43. 摔倒，未躺下。
* A44. 触头（头痛）。
* A45. 触摸肚子（胃痛）。
* A46. 背痛（腰酸）。
* A47. 摸脖子（脖子痛）。
* A48. 恶心，呕吐。
* A49. 拿扇子扇风。
* A50. 拳打/打别人。
* A51. 踢别人。
* A52. 推别人。
* A53. 拍拍对方。
* A54. 用手指指向对方。
* A55. 拥抱其他人。
* A56. 给别人东西。
* A57. 触摸别人的口袋。
* A58. 握手。
* A59. 走向彼此。
* A60. 彼此分开。

## Environment Configuration

### OpenCV Installation
- **Issue**: PEP517 Error when building wheels for opencv-python
- **Target Python Version**: Python 3.6
- **Solution**: Install a specific version of opencv-python:
  ```bash
  pip install opencv-python==4.3.0.38
  ```

### CUDA Environment Setup
- **Steps**:
  ```bash
  conda activate 4d
  export CUDA_HOME=/usr/local/cuda-11.7
  export LD_LIBRARY_PATH=/usr/local/cuda-11.7/lib64:$LD_LIBRARY_PATH
  export PATH=/usr/local/cuda-11.7/bin:$PATH
  ```

## Future Debugging Entries

### Template
```markdown
## [Category]

### [Issue Title]
- **Error**: [Description of the error]
- **Reference**: [Link to external resource or documentation]
- **Solution**: [Steps or method to resolve the issue]
```

## Wish 
In the journey of deep learning exploration, may your code be bug-free and your models achieve state-of-the-art performance. 

Happy coding and debugging!
