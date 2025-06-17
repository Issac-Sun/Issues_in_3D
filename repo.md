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
- **Note**: The datasets are large, refer to the [3DV work](https://github.com/facebookresearch/fairseq/issues/2510) or their preprocessing scripts.

### 4D Semantic Segmentation
- **Issue**: Handling long sequence point cloud videos
- **Reference**: [4D semantic segmentation on Synthia Dataset model code · Issue #4 · hehefan/P4Transformer](https://github.com/hehefan/P4Transformer/issues/4)

### NTURGBD60 Labels (Chinese)
- **List of Actions**:
  - A1. Drinking water
  - A2. Eating/snacking
  - A3. Brushing teeth
  - A4. Combing hair
  - ... (and so on for all labels)

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

### Examples of Future Entries

#### Memory Management
- **Issue**: Out of Memory (OOM) errors during training
- **Reference**: [PyTorch Documentation on Memory Management](https://pytorch.org/docs/stable/notes/cuda.html)
- **Solution**: Reduce batch size, use gradient checkpointing, or upgrade hardware.

#### Model Training
- **Issue**: Model not converging
- **Reference**: [Common Training Issues in Neural Networks](https://example.com/training-issues)
- **Solution**: Adjust learning rate, check data normalization, or modify network architecture.

## Conclusion
By maintaining a structured and categorized debugging repository, you can efficiently track and resolve issues in your deep learning projects. Feel free to add new entries following the provided template.
