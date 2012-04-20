#!/usr/bin/python

import os
import Image
import imghdr

DATE_TIME_ORIGINAL_TAG = 0x9003

def get_date_time_original(file_name):
    i = Image.open(file_name)
    info = i._getexif()
    return info[DATE_TIME_ORIGINAL_TAG]

def list_images(path="."):
    return [f for f in os.listdir(path) if is_image(f)]

def is_image(f):
    return os.path.isfile(f) and imghdr.what(f) in ['jpeg', 'gif', 'png']

def time_as_filename(time):
    return time.replace(' ', '_').replace(':', '.')

def get_new_name(file_name):
    _, ext = os.path.splitext(file_name)
    time = get_date_time_original(file_name)
    new_name = time_as_filename(time)
    return new_name + ext.lower()

def rename_files(path):
    files = list_images()
    for old_name in files:
        new_name = get_new_name(old_name)
        if old_name == new_name: 
            continue
        if os.path.exists(new_name):
            print "WARN: could not rename '%s' to '%s' (already exists)" % (old_name, new_name)
        else:
            print new_name, '<--', old_name
            os.rename(old_name, new_name)

if __name__=='__main__':
    rename_files('.')

