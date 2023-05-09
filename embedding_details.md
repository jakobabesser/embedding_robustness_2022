# Extracted embeddings

This page gives more details about the extracted embeddings.

## Kumar

- Initial code taken from https://github.com/anuragkr90/weak_feature_extractor
- Pytorch  1.0.1.post2
- results and paper: http://www.cs.cmu.edu/~alnu/TLWeak.htm
- fftsize has been changed to 1024 instead of 2048 according to paper and ESC50 results
- make sure to download the .pkl Modle from the github directly (filesize: 19.1 MB) otherwise unpickling erros occur

- sample rate = 44100
- n_fft = 1024 # changed to 1024 according to paper and fitting results on esc50
- hop_length = 512
- n_mels = 128
- trainType = 'weak_mxh64_1024' - model
- pre_model_path = 'mx-h64-1024_0d3-1.17.pkl' - file for model
- featType = 'layer18'

## OpenL3

- music, mel256 input, 512 output size
- https://pypi.org/project/openl3/
- version 0.4.1 (TF2.3)
- (alternative with TF1.14 and openl3 0.3.1.)
- sample rate = 48000

## PANN

- code taken from https://github.com/qiuqiangkong/audioset_tagging_cnn
- model: cnn14_512.pth
- model can be downloaded from https://zenodo.org/record/3576403/
- Pytorch  1.0.1.post2
- no audio panning - arbitrary length passed throug network with global pooling (default from paper)
- see: pythonrepo/idmt/external/pann/inference_main.py
- sample rate = 32000

- window_size = 1024
- hop_size = 320
- fmin = 50
- mel_bins = 64
- fmax = 14000

## PaSST
- code for HEAR2021 challenge: https://github.com/kkoutini/passt_hear21/tree/c02c4b4b367399bebbe20971b674e7c87609228d
- version: 0.0.19
- environment as suggested (torch==1.8.1)
- default parameters: "passt_s_swa_p16_128_ap476"
- structured patchout
- sample rate 32000, mono
- internal parameters (default): n_mels=128, sr=32000, win_length=800, hopsize=320, n_fft=1024, freqm=48,
                             timem=192,
                             htk=False, fmin=0.0, fmax=None, norm=1, fmin_aug_range=10,
                             fmax_aug_range=2000
- embedding size 1296
- embeddings via get_basic_timestamp_embeddings()
- 50ms hopsize, averaged over 1 second snippets -> [5, 1296]

## VGGish
- code taken from https://github.com/tensorflow/models/tree/master/research/audioset/vggish
- model can be downloaded from same page -> vggish_model.ckpt

- parameters: idmt/external/tf_vggish_audioset/vggish_params.py

- NUM_FRAMES = 96  # Frames in input mel-spectrogram patch.
- NUM_BANDS = 64  # Frequency bands in input mel-spectrogram patch.
- EMBEDDING_SIZE = 128  # Size of embedding layer.

- # Hyperparameters used in feature and example generation.
- SAMPLE_RATE = 16000
- STFT_WINDOW_LENGTH_SECONDS = 0.025
- STFT_HOP_LENGTH_SECONDS = 0.010
- NUM_MEL_BINS = NUM_BANDS
- MEL_MIN_HZ = 125
- MEL_MAX_HZ = 7500
- LOG_OFFSET = 0.01  # Offset used for stabilized log of input mel-spectrogram.
- EXAMPLE_WINDOW_SECONDS = 0.96  # Each example contains 96 10ms frames
- EXAMPLE_HOP_SECONDS = 0.96     # with zero overlap.

-	# padding for short files
- MINIMUM_LENGTH_SECONDS = 1
