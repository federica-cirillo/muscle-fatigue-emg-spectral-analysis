# Muscle Fatigue Assessment in Load-Lifting Tasks via Spectral Analysis of the EMG Signal

Bachelor's thesis in **Biomedical Engineering** — University of Naples Federico II (DIETI), Academic Year 2022/2023.

This work investigates the onset of muscle fatigue during manual load-lifting tasks through spectral analysis of the surface electromyographic (sEMG) signal recorded from the lumbar multifidus muscle. The goal is twofold: to detect fatigue as lifting repetitions accumulate, and to evaluate how well spectral features can discriminate between biomechanical risk classes defined by the Revised NIOSH Lifting Equation (RNLE).

## Background

Work-related musculoskeletal disorders (WMSDs) are among the most common occupational health problems, and biomechanical overload during manual material handling is a major risk factor. Compared with traditional observational risk-assessment methods (RNLE, RULA, REBA, OCRA, OWAS, etc.), instrumental and quantitative approaches based on wearable devices offer more objective and repeatable results. Surface EMG is one such method: during fatiguing contractions, the EMG power spectrum shifts toward lower frequencies and the signal amplitude increases, making mean and median frequency informative markers of muscle fatigue.

## Objective

- Detect the appearance of muscle fatigue in lifting tasks from sEMG spectral features.
- Assess the predictive power of these features in separating a **No Risk** condition (LI ≤ 1) from a **Risk** condition (LI > 1), with risk defined through the RNLE.
- Explore the link between muscle fatigue and the potential onset of WMSDs.

## Methods

**Population.** 15 healthy subjects were recruited; 10 were retained for analysis after excluding recordings affected by poor electrode–skin contact or accessory movements.

**Protocol.** Each subject performed two trials of consecutive lifts (squat technique, two-handed grip):
- *First trial* — No Risk class (LI = 0.5)
- *Second trial* — Risk class (LI = 1.3)

The lifting index was computed with the RNLE by varying load weight, lifting height, and frequency.

**Acquisition.** sEMG signals were collected with the **KineLive** wearable system (sampling frequency 1600 Hz), focusing on the channels placed over the lumbar multifidus muscles.

**Signal processing (MATLAB).**
- Band-pass Butterworth filter (8th order, 15–400 Hz)
- Envelope extraction via low-pass Butterworth (4th order, 20 Hz) and Savitzky–Golay smoothing (3rd order)
- Manual thresholding to segment each lift into a Region of Interest (ROI)
- Per-ROI spectrum computation and feature extraction

**Features (frequency domain).** Power, peak power, peak frequency, median frequency, mean frequency, kurtosis, skewness.

**Statistics.** Linear regression of mean and median frequency against lift number to assess trends; statistical analysis in IBM SPSS using the Shapiro–Wilk normality test followed by the non-parametric Wilcoxon test for paired data (significance level α = 0.05).

## Results

- In the **No Risk** condition, mean and median frequencies showed no significant downward trend across repetitions; in the **Risk** condition, both frequencies decreased as lifts accumulated, consistent with the onset of fatigue.
- All extracted features yielded a p-value below 0.05, meaning each one significantly discriminated the No Risk class from the Risk class.
- A significant increase in signal power (amplitude) and changes in kurtosis and skewness confirmed the leftward shift and reshaping of the spectrum from No Risk to Risk.

## Conclusions

Spectral feature analysis of the sEMG signal proves to be a useful tool both for assessing muscle fatigue and for classifying biomechanical risk in manual load-lifting tasks, and therefore a promising preliminary indicator of the risk of related musculoskeletal disorders. Future work could use these features to train machine learning algorithms for automatic risk prediction.

## Repository contents

- `Tesi_CirilloFederica.pdf` — full thesis 

## Author

Federica Cirillo — Biomedical Engineering, University of Naples Federico II
Supervisor: Prof. Maria Romano · Co-supervisors: Prof. Paolo Gargiulo, Eng. Leandro Donisi, PhD

