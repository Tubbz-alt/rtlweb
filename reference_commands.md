A series of commands to keep on the top of my head while designing this little project.

# Listen to basic mono FM
`rtl_fm -g 30 -f 99.9M -M wbfm -F 0 -s 160k -o 4 -E deemp | ffmpeg -f s16le -ar 32k -i - /tmp/dank.wav -y`

# Ideal MPX Capture
`rtl_fm -M fm -l 0 -A std -p 0 -s 171k -g 20 -F 9 -f 94.1M | redsea -u`

# HLS Stream with ffmpeg
`ffmpeg -f alsa -i pulse -c:a aac -b:a 192k  -hls_flags delete_segments -segment_list_size 40 -segment_time 10 -f hls /tmp/test.m3u8`
