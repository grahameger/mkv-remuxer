import sys
from os import listdir
from os import getcwd
from os.path import isfile, join

# Gets rid of nasty spaces in filenames
def shellquote(s):
    return s.replace("'", "'\\''")

# get the current path
path = shellquote(getcwd())

# get a list of all the files in the path
onlyfiles = [f for f in listdir(path) if isfile(join(path, f))]

# declare an array that will hold only files with MKV extension
allshows = []

for file in onlyfiles:
	# gets all the mkv files
	if 'mkv' in file:
		file = shellquote(file)
		allshows.append(file)
		pass

import os

# remux all of the shows
for show in allshows:
	os.system('ffmpeg -i ' + show + ' -vcodec copy -acodec copy ' + '-metadata:s:a:0 language=eng ' + os.path.splitext(show)[0] + '.mp4')
