	Quản lý Code là một trong những thao tác cơ bản để nắm bắt rõ trạng thái và quá trình phát triển Project. Các quy tắc quản lý File và Code.
		1. Script nằm cạnh Scene mà nó điều khiển
			EX: player/
					player.gd
					player.tscn
		2. Chỉ được tạo Scripts khi có hành vi riêng và logic riêng
		3. Dữ liệu tĩnh ( Static Data ) là các chỉ số nhân vật, cốt truyện, item 
			info, định nghĩa -> Được lưu trong data/ => File json, resource (.tres)
		4. Dữ liệu Runtime (realtime data) là chỉ số HP hiện tại, điểm số, trạng 
			thái -> Được lưu trong Ram ở các node, autoload