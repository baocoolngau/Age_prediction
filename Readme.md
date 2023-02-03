## THÔNG TIN CÁC FILE ĐÍNH KÈM
1. **221IS2902_DAwP_R_FinalProject_Group HI.docx**
     
    Đây là file báo cáo tổng hợp của đồ án. Các nội dung chính bao gồm: Tổng quan đồ án, cơ sở lý thuyết, quy trình lập trình xây dựng mô hình, đánh giá kết quả và kết luận
2. **221IS2902_DAwP_R_FinalProject_Group HI.pdf**

   File báo cáo tổng hợp ở định dạng pdf

3. **221IS2902_DAwP_R_FinalProject_Group HI_thuyet_trinh.pdf**

   File thuyết trình của nhóm

4. **221IS2902_DAwP_R_FinalProject_Group HI.jpynb**

   File source code của đồ án ở định dạng notebook

5. **221IS2902_DAwP_R_FinalProject_Group HI.h5**

   Model CNN đã được train của đồ án
 
6. **221IS2902_DAwP_R_FinalProject_Group HI.xml**

    Tệp XML này chứa một mô hình với thuật toán phân tách vật thể đã được huấn luyện từ trước nên được dùng để tách khuôn mặt từ ảnh trong đồ án này
    

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
     
     
     
