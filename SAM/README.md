# Finetuning Segment Anything Model(SAM)
This is notebook is copied from the following [SAM-Finetuning](https://github.com/alaminkawsar/Transformers-Tutorials/tree/master/SAM). I have changed a little bit in the following code:

1. Modified processing parameter.
```
inputs = self.processor(image, input_boxes = [[prompt]], segmentation_maps=ground_truth_mask, return_tensors="pt")

```
Before it can't handle the different mask size. But now It can handle any mask size and image size. Obviously, mask should be binary format or the mask shape will be (W,H) but not 3 or 2 channel image.
2. Added the following code to save the model and processor.
```
model.save_pretrained("SAM")
processor.save_pretrained("SAM")
```

You can find all the details from huggingface:
- [Huggingface-SAM](https://huggingface.co/docs/transformers/main/en/model_doc/sam)



