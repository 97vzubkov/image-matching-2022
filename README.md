# Image-Matching-2022
Here is my solution for the competition that took place on the Kaggle platform where I entered the top 16% of all participants. But before that, a little introduction..

It was was my first experience competing on Kaggle as well as working on computer vision task especially on image matching. I would like to deeply appreciate the Kaggle staff, Google Research and CVPR 2022 for hosting this exciting competition and their help throughout the entire distance. They introduced me to the new field of feature matching in the most gentle way possible and made my learning sooooo much easier!

### My solution.

All the models used are pretrained due to the nature of training set which strongly differed from testing set as well as my limited resources: Kaggle Notebooks and Colab Pro.

- pretrained LOFTR with longest edge equal to 1200, MAGSAC++ (0.200, 0.9999, 250000) + TTA left-right (private score = 0.755)
- pretrained DISK with image size (768, 1024), DEGENSAC (0.95, 0.99, 2000) + Kornia match cnn (private score = 0.500)
- pretrained DKM with MAGSAC++ (0.3, 0.9999, 25_000) + TTA left-right (private score = 0.680)
- pretrained SuperPoint + Superglue with outdoor weights, max_points = 1024 and MAGSAC++ (0.25, 0.99999, 10000) (private score = 0.567)

Bigger image size and TTA gave a boost on the leaderboard.

For the final submission I'be just used single LOFTR model that, in result, gave me 102 place out of 642.

### What I've done wrong and what didn't help.

- Ensemble of models. I understood that an ensemble of models would improve the result and tried to do it even quite early, but due to inexperience in using this technique, I connected the matrices incorrectly and did not get the proper result (as it turned out after the competition, this was the key ingredient for medal zone).
- HardNet + AdaLAM
- Training LOFTR
- Using AdaLam to filter matches
- Adaptive F/H strategy. The main idea of this is to remove some wrong matches using Homography matrix. In contrast to Fundamental matrix, Homography assumes that points are planar.

It was an unforgettable couple of weeks, where I learned a lot of new things for myself and also fell in love with competitions. Yes, I made some mistakes, but during and after the competition, I learned important lessons from them.
