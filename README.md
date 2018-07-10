Task 3: Duplicate analysis

We have many duplicate submissions in AcousticBrainz, files that represent the same music recording (and have the same MBID) but were submitted by many people. These files could be from different sources (e.g. different CDs issues, a remastered CD, a recorded vinyl, a radio edit) and could be encoded using different formats (MP3, Flac, AAC). We are providing a dataset of only songs with more than 1 submission.

We also know that some submissions in AcousticBrainz have been incorrectly labeled. That is, the contents of the file which was analysed is not the file which the MBID label indicates. The goal of this task is to find which submissions in the provided dataset are mislabeled.

Analyse these files and see if duplicate files which should be the same have similar descriptor values. Some examples of values that you could compare include:

length
bpm
average loudness
onset rate
beat positions
chords histogram
hpcp mean
key_key and key_scale
replaygain
tuning frequency
This data is distributed as an archive of json files, in the format that we store the data in AcousticBrainz. You won't need all of the data included in these files, and so should first reduce the data to just the necessary values, and then work with that data. You can loop through each of the files, extract each of these features, and store them in a CSV file.

You should experiment with each feature and see if you can identify for each one a value which appears to be different in one duplicate file to all of the others. For example, if a length is more than 20 or 30 seconds different to the mean of all lengths for this file, it may be an incorrect file.
For values such as the average loudness or means of hpcp values you could see if any value falls more than 1 standard deviation from the mean of this value over all duplicates.
For the key key and scale values you can check if any value is more common than the others (mode), and see which duplicates do not share this common value.
If a particular file deviates from normal in many of these measures, you can be more sure that it is a mis-labeled duplicate.

Data files

ab-duplicates100-2016-03-02.tar.bz2 (134MB)
ab-duplicates1000-2016-03-02.tar.bz2 (825MB)

Contains json files with AcousticBrainz features for files which have been submitted multiple times. The filename of these files contains the MusicBrainz id of the submission, and an ordinal number representing the submission order to AcousticBrainz.

The first file only contains data for 100 MBIDs, and so is smaller. The final analysis should be done on the second, larger file.
