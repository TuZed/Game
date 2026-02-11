	Trong 1 project, các file và thư mục sẽ chia theo VAI TRÒ chứ không chia theo loại file. Chia các file có hệ thống và đảm nhận các VAI TRÒ khác nhau.
			EX: game sẽ có những phần gì ?
				-> Nhân vật
				-> Kẻ địch
				-> Level
				-> UI
				-> Hệ thống lưu
				-> Hệ thống âm thanh
				-> Cốt truyện
				-> Dữ liệu cấu hình
			=> nên đặt tên thư mục phản ảnh cấu trúc đó, vai trò đó.
			Ví dụ triển khai thực tế:
				res://
					│
					├── core/                # Hệ thống lõi
					│   ├── game_manager/
					│   ├── save_system/
					│   ├── audio_system/
					│   └── config/
					│
					├── gameplay/            # Gameplay chính
					│   ├── player/
					│   ├── enemy/
					│   ├── npc/
					│   ├── items/
					│   └── mechanics/
					│
					├── levels/
					│   ├── level1/
					│   ├── level2/
					│   └── world_map/
					│
					├── ui/
					│   ├── main_menu/
					│   ├── hud/
					│   └── dialogs/
					│
					├── data/                # Dữ liệu thuần
					│   ├── story/
					│   ├── stats/
					│   └── balance/
					│
					├── assets/
					│   ├── sprites/
					│   ├── audio/
					│   ├── fonts/
					│   └── tilesets/
					│
					└── main/
					    └── Main.tscn
					    
				core/ – bộ não toàn cục
				-> Chứa:
					- GameManager
					- Save
					- Global config
					- AudioManager
				=> Những thứ dùng ở mọi nơi
				
				gameplay/ sẽ là phần làm nhiều nhất
				-> Ví dụ:
					gameplay/player/
					    Player.tscn
					    player_data.tres
					    player_animation.tscn
				=> Scene + dữ liệu + logic ở cùng 1 chỗ . Không tách Script sang 
				chỗ khác.
				
				UI/ Rất quan trọng nếu làm mobile, thay đổi layout trong tương lai
				-> Tách UI ra khỏi gameplay. Quản lý UI riêng với hệ thống game
				
				data/ Chứa các cấu hình hệ thống, thông tin quan trọng
				-> File Json, source, cấu hình, thông tin, cốt truyện
				=> Không chứ Node
				assets/ Chứa các file thuần, tài nguyên gốc
				-> Không chứa các scripts
				=> Chỉ chứa file tài nguyên thuần

