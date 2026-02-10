	Code là nơi mô tả lại những tương tác của người dùng cho máy tính thực thi, hay dễ hiểu phổ biến code là trung gian giữa việc chuyển giao từ ngôn ngữ logic người sang ngôn ngữ và logic máy. Nhưng trong vai trò của việc làm game , code đóng vai trò là khu vực xử lý các thao tác của người dùng ( như nhấn nút, voice, di chuyển nhân vật ) gửi các tín hiệu về hệ thống, và xử lý các logic này để phản hồi lại người dùng.
		-> Khi đến X = xảy ra sự kiện 
		-> Mỗi giây = cập nhật điều gì
		-> Người chơi bấm phím = phản ứng ra sao
			
	Code game sẽ chạy hệ thống theo thời gian thực ( realtime ) , vì phải đợi người chơi thao tác ( nhấn, voice, di chuyển ) thì mới thực thi và phản hồi người chơi được.
		-> Game chạy theo vòng lặp ( loop )
	
	Gameloop là trái tim của code game, mọi game đều xoay quay vòng lặp ( loop )
		-> While (game is running) => thực thi hành động
	
	Code game năm ở tầng trung gian giữa Engine và Logic máy , Engine làm sẵn các thao tác input-render-physics sau đó đưa các thông tin này đến CODE , từ đây hệ thống logic máy tính mới bắt đầu thực thi thao tác và phản hồi sau khi đã được hiểu mã CODE.