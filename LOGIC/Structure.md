	Chúng ta sẽ sử dụng Engine Godot để làm game 2D, vì nó sinh ra tối ưu cho game 2D và là 1 mã nguồn mở miễn phí. Nhẹ hơn các Engine khác, Engine Godot là 1 cỗ máy chạy game, nó quản lý cửa sổ, render hình ảnh, âm thanh, input (chuột , bàn phím , màn hình), physics (các va chạm), Scene , Node.
		-> Node là gì? 
			Node = 1 khối chức năng nhỏ nhất trong Godot
			EX: hiểu đơn giản Node giống như 1 bộ phận của 1 cỗ máy, chẳng hạn
				trong cái xe sẽ có động cơ, bánh xe, tay lái => mỗi cái là 1 node.
				Mỗi node chỉ làm đúng nhiệm vụ của nó, và không làm gì ngoài phạm
				vi được thiết lập.
		-> Bên trong Node có gì?
			Mỗi node có :
				Thuộc tính (Property)
					-position
					-rotation
					-scale
				Hàm (Function)
					- _process()
					- _ready()
				Tín hiệu (Signal)
					-body_entered
					-pressed
		-> Node được tổ chức thành cây ( Tree )
			EX: Node
				├─ Node
				│   └─ Node
				└─ Node
			=> Quy tắc : -Node cha xoá -> node con mất
						-Node con kế thừa transform của Node cha, trong đó 
						transform là cách 1 vật tồn tại trong không gian 2D
						một transform gồm 3 thứ chính là:
							- Position - vị trí (x,y)
							- Rotation - xoay (độ)
							- Scale - phóng to/ thu nhỏ
						Hiểu đơn giản là cấu trúc vị trí của Node con sẽ phụ 
						thuộc vào tham số của Node cha chứ không đưa thẳng tham
						số vào toàn cục (global)
							EX: Node cha có toạ độ (x,y)=(100,200) tại global
								Thì nếu Node con có toạ độ (x,y)=(20,30) tại
								Node cha thì trong global, toạ độ Node con chính
								là tham số toạ độ Node cha + tham số toạ độ Node
								con . Lúc này trong global ta sẽ thấy Node con ở
								toạ độ (x,y) = (120,230) 
									-> toạ độ Node cha (100,200) + toạ độ Node 
									con (20,30)=> ra toạ độ tại global (120,230)
		
		-> Scene là gì?
			Scene = 1 cây Node được lưu thành file dưới dạng *.tscn và có thể sử
			dụng được nhiều lần => Scene giống như 1 bản thiết kế kết nối các Node
			chức năng lại với nhau.
				EX: Player (CharacterBody2D)
					├─ Sprite2D
					├─ CollisionShape2D
					└─ Camera2D
				=> Cả đống này gộp lại thành Scene tên Player.tscn
		-> Scene dùng làm gì?
			Scene có thể đại diện cho các bộ Tree có chức năng và nhóm thuộc tính 
			khác nhau như cụm player = nhân vật, enemy = kẻ địch, lv1 = màn chơi,
			v.v....
			=> mọi thứ trong Godot đều là Scene
		-> Scene cũng là 1 Node
			Bản chất Scene cũng là 1 Node, Root Node của Scene = Node và Scene có
			thể gắn vào Scene khác hoặc Spawn (instance) nhiều lần
			EX: Player.tscn được Instance vào Lv1.tscn
					=> 1 Player scene = 1 Node trong Lv1
		
		-> Instance là gì? 
			Instance là tạo ra 1 bản sao của Scene
			EX: 1 Enemy.tscn được Instance 10 lần = 10 kẻ địch
				trong cụm Scene Lv lúc này sẽ có 10 kẻ địch nhưng bản chất đều từ 
				một Scene gốc là Enemy.tscn
			