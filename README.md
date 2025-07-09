import yt_dlp
def download_youtube_video(url, save_path="."):
    ydl_opts = {
        'outtmpl': f'{save_path}/%(title)s.%(ext)s',
        'format': 'best'
    }
    with yt_dlp.YoutubeDL(ydl_opts) as ydl:
        ydl.download([url])
video_url = input("Enter the YouTube video URL: ")
download_youtube_video(video_url, save_path=".")



"""def download_youtube_video(url, save_path="."):
ประกาศฟังก์ชันชื่อ download_youtube_video ที่รับพารามิเตอร์ 2 ตัว:

url: ลิงก์วิดีโอ YouTube

save_path: ตำแหน่งโฟลเดอร์ที่จะบันทึกไฟล์ (ค่าเริ่มต้นคือ "." หมายถึงโฟลเดอร์ปัจจุบัน)

python
Copy
Edit
    ydl_opts = {
        'outtmpl': f'{save_path}/%(title)s.%(ext)s',
        'format': 'best'
    }
สร้าง dictionary ชื่อ ydl_opts เพื่อกำหนดตัวเลือกในการดาวน์โหลด:

'outtmpl': ระบุรูปแบบชื่อไฟล์ที่บันทึก เช่น ถ้า save_path="." และวิดีโอชื่อ "MyVideo" จะบันทึกเป็น ./MyVideo.mp4 (หรือสกุลอื่น ๆ ตามจริง)"""

