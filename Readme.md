## THÔNG TIN CÁC FILE ĐÍNH KÈM
4. **Source_code.jpynb**

   File source code ở định dạng notebook.

5. **model_4.h5**

   Model CNN đã được train.
 
6. **haarcascade_frontalface_default.xml**

    Tệp XML này chứa một mô hình với thuật toán phân tách vật thể đã được huấn luyện từ trước nên được dùng để tách khuôn mặt từ ảnh.
    

## CÁCH THỰC THI CODE CHO NGƯỜI DÙNG
1. Chuẩn bị môi trường
    
    * Google colab (môi trường máy chủ - hosted runtime)
    
    Mở file Source_code.jpynb bằng google colab ( file -> open notebook).
    
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20204700.jpg)
    
   
   Tải tệp model model_4.h5 và tệp haarcascade_frontalface_default.xml lên thư mục
   
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20211322.jpg)
     
2. Chạy code
* Chạy Ô khai báo thư viện

      import pandas as pd
      import numpy as np
      import os
      import cv2
      import matplotlib.pyplot as plt
      import seaborn as sns
      import skimage
      import sklearn
      import warnings
      from tqdm.notebook import tqdm
      from pathlib import Path
      warnings.filterwarnings('ignore')
      import tensorflow as tf
      from keras.preprocessing.image import load_img
      from keras.models import Sequential, Model
      from keras.layers import Dense, Conv2D, Dropout, Flatten, MaxPooling2D, Input

* Chạy ô tạo hàm phân tách khuôn mặt từ ảnh

      # detect face from test image
      haar_file = 'haarcascade_frontalface_default.xml'
      face_cascade = cv2.CascadeClassifier(haar_file)
      (width, height) = (128, 128)
      def detect_face(path):
          out_put = []
          for i in path:
              im = plt.imread(i)
              faces = face_cascade.detectMultiScale(im, 1.3, 4)
              for (x, y, w, h) in faces:
                  cv2.rectangle(im, (x, y), (x + w, y + h), (255, 0, 0), 2)
                  face = im[y:y + h, x:x + w]
                  face_resize = cv2.resize(face, (width, height))
              out_put.append(face_resize)
          out_put = np.array(out_put)
          return out_put
          
* Chạy ô tạo hàm trích xuất đặt trưng từ khuôn mặt

      # extract_feature test image function
      def extract_features_test(images):
          features = []
          for i in images:
              gray = cv2.cvtColor(i, cv2.COLOR_BGR2GRAY)
              features.append(gray)
          features = np.array(features)
          features = features/255
          return features
    
* Tải ảnh test lên

* Load CNN model

        cnn_model = tf.keras.models.load_model('saved_models/model_4.h5')

* V là xong..Chạy ô test thôi nào :muscle:  :muscle:

      # test for user image
      import matplotlib.pyplot as plt
      path = 'z3850238868064_1a4dfabf35a46684ef9616eb57b8ab35.jpg'
      my_img = plt.imread(path)
      my_face = detect_face(np.array(path).reshape(1,))
      my_face_features = extract_features_test(my_face)
      pred = cnn_model.predict(my_face_features.reshape(1, 128, 128, 1))
      pred_age = round(pred[0][0])
      print("Predicted Age:", pred_age)
      plt.axis('off')
      plt.imshow(my_img);
      1/1 [==============================] - 1s 544ms/step
      Predicted Age: 20
      
     ![image](https://user-images.githubusercontent.com/116325378/216722914-91eda91d-1d54-4c0e-951c-1e1f98db6233.png)

   Kết quả chính xác 100%. Xác nhận từ tác giả và cũng là người trong hình =))) :stuck_out_tongue:  :stuck_out_tongue_closed_eyes:

  Đối với môi trường máy cục bộ (local runtime) thì phải cài đặt tất cả các thư viện trong ô khai báo thư viện trước khi chạy bằng lệnh sau:
  
  1. **Google colab**
  
         !pip install library_name
  2. **VScode**
         
         pip install library_name
     
     
     
