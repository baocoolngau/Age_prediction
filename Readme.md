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
    
    Mở file 221IS2902_DAwP_R_FinalProject_Group HI.jpynb bằng google colab ( file -> open notebook).
    
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20204700.jpg)
    
   
   Tải tệp model 221IS2902_DAwP_R_FinalProject_Group HI.h5 và tệp 221IS2902_DAwP_R_FinalProject_Group HI.xml lên thư mục
   
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20211322.jpg)
     
  2. Chạy code
      * Chạy ô khai báo thư viện
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20212255.jpg)
      * Chạy ô tạo hàm phân tách khuôn mặt từ ảnh
      ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20213358.jpg)
      * Chạy ô tạo hàm trích xuất đặt trưng từ khuôn mặt
      
        ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20221602.jpg)
      * Tải ảnh test lên
      
        ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20214410.jpg)
      * Load CNN model
        
        Chỉnh sửa lại đường dẫn thành 221IS2902_DAwP_R_FinalProject_Group HI.h5
        
          ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20220935.jpg)
     
     * V là xong..Chạy ô test thôi nào :muscle:  :muscle:
     
           # Tên file ảnh
           path = ''
           
       ![](file:///C:/Users/Admin/Pictures/Screenshot%202022-11-29%20221733.jpg)
       
         Kết quả chính xác 100%. Xác nhận từ tác giả và cũng là người trong hình =))) :stuck_out_tongue:  :stuck_out_tongue_closed_eyes:
     
  Đối với môi trường máy cục bộ (local runtime) thì phải cài đặt tất cả các thư viện trong ô khai báo thư viện trước khi chạy bằng lệnh sau:
  
  1. **Google colab**
  
         !pip install library_name
  2. **VScode**
         
         pip install library_name
     
     
     
