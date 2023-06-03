# ffmpeg-code-summary-table


動画から音声摘出　ffmpeg -i "download.mp4" -vn -acodec copy "audio.mp4"

動画に指定した音声を上書きする　ffmpeg -i "out.mp4" -i "audio.mp4" -c:v copy -c:a aac -map 0:v:0 -map 1:a:0 "videooo.mp4"

静止画像を動画に変換30fps ffmpeg -framerate 30 -i %15d.png -vcodec libx264 -pix_fmt yuv420p oust.mp4
ffmpeg -r 30 -i %15d.png -vcodec libx264 -pix_fmt yuv420p out.mp4

%15d.png
%00000000042557d.png

動画を静止画像に変換download.mp4動画ファイルを入力としてpng形式の静止画像に変換ファイル名がimage_0001.pngから始まるように出力します
ffmpeg -i download.mp4 -vcodec png image_%04d.png

aaa.ts動画をaaa.mp4に変換
ffmpeg -i "aaa.ts" -vcodec copy -acodec copy "aaa.mp4"

2つの動画ファイルを結合。具体的にはaaa.mp4の音声をコピーし、out.mp4に音声ストリームをAACコーデックでエンコード、output.mp4という名前の動画ファイルを出力
ffmpeg -i "aaa.mp4" -i ""out.mp4" -c:v copy -c:a aac output.mp4

ビデオストリームと音声ストリームのエンコードは変更せず、aaa.movをas.mp4に変換
ffmpeg -i "aaa.mov" -vcodec copy -acodec copy "as.mp4"
