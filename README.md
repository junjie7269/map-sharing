import folium

# 創建一個地圖，設置中心點為中國文化大學的經緯度
m = folium.Map(location=(25.0845, 121.5645), zoom_start=12)

# 拍貼機位置及名稱
photobooths = [
    (25.0523, 121.5190, "SnapShot 中山創始店"),
    (25.0422, 121.5065, "SnapShot 西門町店"),
    (25.0330, 121.5645, "SnapShot 信義店"),
    (25.0845, 121.5645, "SnapShot 士林捷運店"),
    (25.0438, 121.5075, "Cut Cut+ 韓式寫真館"),
    (25.0145, 121.4630, "板橋大遠百店"),
    (25.0340, 121.4520, "新莊小胖不減肥概念店")
]

# 標記拍貼機位置，並使用自訂圖標
for lat, lon, name in photobooths:
    folium.Marker(
        location=(lat, lon),
        popup=name,
        icon=folium.Icon(color='blue', icon='info-sign')
    ).add_to(m)

# 將地圖保存為 HTML 文件
m.save('拍貼機位置')

# 提示完成訊息
print("地圖已經生成並保存為 拍貼機位置")
