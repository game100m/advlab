import yt_dlp //นำเข้าไลบรารี yt_dlp ซึ่งใช้สำหรับดาวน์โหลดวิดีโอหรือเสียงจาก YouTube และเว็บไซต์อื่น ๆ ที่รองรับ

def download_youtube_video(url, save_path="."): 
"""download_youtube_video(url, save_path=".")
ฟังก์ชันนี้รับ 2 พารามิเตอร์:
url: ลิงก์วิดีโอ YouTube ที่จะดาวน์โหลด
save_path: เส้นทางที่ใช้บันทึกวิดีโอ (ค่าเริ่มต้นคือโฟลเดอร์ปัจจุบัน ".")"""
    ydl_opts = {
        'outtmpl': f'{save_path}/%(title)s.%(ext)s', ////outtmpl: เป็นเทมเพลตชื่อไฟล์ที่บันทึก โดยใช้ชื่อวิดีโอ (%(title)s) และนามสกุลไฟล์ (%(ext)s) format: ดาวน์โหลดไฟล์วิดีโอคุณภาพดีที่สุด (best)

python
        'format': 'best'
    }
    with yt_dlp.YoutubeDL(ydl_opts) as ydl:   ///สร้างอ็อบเจกต์ YoutubeDL โดยใส่ ydl_opts (options)เรียกใช้ .download([url]) เพื่อเริ่มดาวน์โหลดวิดีโอ
        ydl.download([url])

# Example usage
# video_url = ""
# print("Youtube URL : ") 
# input(video_url)
video_url = input("Enter the YouTube video URL: ") ///แสดงข้อความให้ผู้ใช้กรอก URL ของวิดีโอ YouTube
# video_url = "https://www.youtube.com/watch?v=DhuGP_-zMxU"
download_youtube_video(video_url, save_path=".") ///ส่ง URL ที่ผู้ใช้กรอกเข้าไปในฟังก์ชัน พร้อมบันทึกไฟล์ลงในโฟลเดอร์ปัจจุบัน
