# Predictive-Maintenance-Project
Predicting failure rate of an encoder component using random forest regressor.

Introduction: What is predictive maintenance? Condition-based maintenance involves performance monitoring and equipment condition monitoring during regular operation to reduce the chances of a breakdown. Encoder is a device that is used to convert mechanical motion into the analog and digital signal. In this project I basically have the data related to encoders.

Problem Statement: · question: Model the err, and err-f  columns for individual 'scanners' to show an expected  failure rate of the encoder component. 
Scanners are basically divided into 2 groups: one that never fails, the failure rate which is below 12% and the encoder which fails and its failure rate is above 12%.

Description of dataset: ID, date of encoder installed, min, max, err, err-f, min-f, max-f, pixels, updated date of encoder.
Err: In the context of encoders, "err" usually refers to the error between the desired output of the encoder and the actual output of the encoder. This error can arise due to various reasons such as noise in the input data, non-linearities in the encoder architecture, or suboptimal encoder parameters.
Err-f:  On the other hand, "errf" typically refers to the error function used to calculate the error between the desired and actual outputs of the encoder. This error function is used to guide the encoder's optimization process towards minimizing the error between the desired and actual outputs.
Min-Max: In the context of encoders, "min" and "max" typically refer to the minimum and maximum values that can be encoded by the encoder. These values are usually specified by the encoder manufacturer and are important to know when using the encoder to measure or control a system.
Mind-Maxf: "Minf" and "maxf" are not commonly used terms in the context of encoders,. It's possible that they could be shorthand for "minimum frequency" and "maximum frequency", which could be important parameters for some types of encoders (such as rotary encoders that output a digital signal). However, without more context it's difficult to say for sure.
Pixels: In the context of an encoder, pixel values refer to the numerical values assigned to each pixel in an image or video frame. These values typically represent the brightness or color intensity of the pixel and are often represented as integers ranging from 0 to 255 in an 8-bit color depth system.
Note that we don't have a failure rate in our dataset, we need to make a simple calculation to get the failure rate for each encoder component. Formula is (err/errf)*100% or (err/errf)*1
This is the description of the dataset.

My approach to solve the problem: • Firstly I calculated the failure rate using excel workbook.
• The Scanner column in my dataset has both a combination of text and number and extracted both. And replaced categorical value with numerical value. And then dropped my scanner column.
•Date column in my dataset is in this format yyyy-mm-dd, So I separated them using the pandas to_datetime method. And then drop the Date column.
•Checking for null values and filling them with the average value.
•Splitting the data using sk-learn train test split method.
•Training the model using different regression models and predicting the failure rate of the encoder entered.
•Accuracy of the model is estimated by r square, mse, mae, r mse. 
•In this case I have used Random Forest Regressor to predict the failure rate.
Implementation: Using python’s flask framework designed a website where the user can just enter the details and get his failure rate predicted.
