# -X-ray-Image-Denoising-with-Filters-and-Metric-Evaluation-for-Digtal-Image-Processing
This project demonstrates image denoising on a grayscale X-ray image affected by Salt-and-Pepper noise using various filtering techniques. It also evaluates the performance of each method using PSNR (Peak Signal-to-Noise Ratio) and SSIM (Structural Similarity Index Measure).
📂 Project Overview
•Load and normalize a grayscale X-ray image.
•Introduce salt-and-pepper noise artificially.
•Apply four denoising techniques:
•Median Filtering
•Gaussian Blur
•Bilateral Filtering
•Non-Local Means Denoising
•Compare the effectiveness of each method using PSNR and SSIM metrics.
•Display the results using matplotlib.

📸 Sample Output
•Visual comparison between the original, noisy, and restored images.
•Bar plots for PSNR and SSIM across all denoising methods.

📦 Dependencies
•Make sure the following libraries are installed:
pip install opencv-python-headless numpy matplotlib scikit-image
🧪 How to Run
•Place your grayscale X-ray image in the same directory as the script.
•Rename it to x-ray2.jpg (or modify the filename in the script).
•Run the script:
python denoise_xray.py

🛠 Code Highlights
🔧 Add Salt-and-Pepper Noise
def add_salt_pepper_noise(img, amount=0.09):
Adds synthetic noise to test the performance of filters under extreme conditions.

🧹 Denoising Filters
restored_median = cv2.medianBlur(noisy_image, 3)
restored_gaussian = cv2.GaussianBlur(noisy_image, (5,5), 0)
restored_bilateral = cv2.bilateralFilter(noisy_image, d=9, sigmaColor=75, sigmaSpace=75)
restored_nlmeans = cv2.fastNlMeansDenoising(noisy_image, None, h=10, templateWindowSize=7, searchWindowSize=21)

📊 Image Quality Evaluation
psnr_vals = [psnr(image, r) for r in restored_images]
ssim_vals = [ssim(image, r) for r in restored_images]
Calculates how close the denoised image is to the original using PSNR and SSIM.

📈 Results Example
•Median Filter: Great for salt-and-pepper removal.
•Gaussian Blur: Slightly blurs edges.
•Bilateral Filter: Retains edges while smoothing noise.
•Non-Local Means: High quality, but computationally expensive.

📃 License
•This project is for educational purposes and open-source learning.
