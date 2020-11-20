# cli_ffmpeg
a bunch of ffmpeg commands


mov to mp4 

  `ffmpeg -i input.mov -qscale 0 output.mp4`

mp4 smaller 

  `ffmpeg -i input.mp4  -vcodec h264 -acodec mp2 output.mp4`

remove audio

  `ffmpeg -i input.mp4 -c copy -an $output_file`

To convert video to gif 
  
  `ffmpeg -ss 30 -t 3 -i input.mp4 -vf "flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop 0 output.gif`

  `ffmpeg -i input.mp4 -vf "fps=10,scale=1000:-1:flags=lanczos,split[s0][s1];[s0]palettegen[p];[s1][p]paletteuse" -loop 0 output.gif`
