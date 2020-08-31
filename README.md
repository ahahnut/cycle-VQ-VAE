# cycle-VQ-VAE
Audio-Visual Autoencoding for Privacy-Preserving Video Streaming

## Requirements
It requires python3, python3-pip and the packages listed in [requirements.txt](requirements.txt).

To install the required packages:
```
pip3 install -r requirements.txt
```

## Pre-processing Data
We use `Matlab_File/extract_audio.m` to pre-process the `Source_Data` to `Data` for training. You also can use your own video to train the model.

## Train cycle-VQ-VAE model
```
python src/main.py --results_path="results/unshuffled/" --use_kaiming_normal=True --decay=0.99 --loss_plot_name="loss_ema_norm_he-et-al.png" --model_name="model_ema_norm_he-et-al.pth" --original_images_name="original_images_ema_norm_he-et-al.mat" --crypto_images_name="crypto_images_ema_norm_he-et-al.mat" --validation_images_name="validation_images_ema_norm_he-et-al.mat" --unshuffle_dataset
```
`original_images_ema_norm_he-et-al.mat` is for original images.

`crypto_images_ema_norm_he-et-al.mat` is for encoded images.

`validation_images_ema_norm_he-et-al.mat` is for decoded images.

### The Difference between F2F and V2V
Codes in `src/encoder.py`

```
x, _ = self._rnn(x, None)
```

## Tranfer .mat Files into Images and Video
We use `Matlab_File/save_image.m` to transfer `.mat` to images, and use `Matlab_File/image_to_video.m` to transfer images into video.

## Demo Results
`Demo_Result/F2F/images`
`Demo_Result/F2F/video`
`Demo_Result/V2V/images`
`Demo_Result/V2V/video`

### Reference
This project is based on `https://github.com/swasun/VQ-VAE-Images`

### Tips
If you have any questions about our work, please do not hesitate to contact us by emails.
