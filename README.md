# Basketball-Players-Activities-Recognition-Using-CNN

Overview presentation:
https://www.youtube.com/watch?v=MKoiuSpsWig

Basketball Game Activity Recognition 

Data overview:
	- 5+1 classes (shooting, layups, dribbling, running, walking and null) of basketball specific movements 
	- two subjects
	- sensors:
		- eSense (left ear @50Hz ±8g)
		- Bangle.js (right wrist (dominant hand) @92Hz ±8g)
		- Bangle.js (right ankle @92Hz ±8g)
	- files
		- wrist + ankle: one (or two) csv-file(s) per activity and subject 
			- columns: timestamp, acc_x, acc_y, acc_z
		- earbud: one csv-file per subject
			- columns: timestamp, device_name, acc_x, acc_y, acc_z, gyr_x, gyr_y, gyr_z, label

Folders:
	- sensor_data: collected data from each sensor per each subject

First steps + general hints:
	1. Correct the timestamp within the Bangle.js files - as the first timestamp is correct within each file and you know at which rate was sampled, you can caculate the correct timestamp 
	   for each record.
	2. Upsample or downsample either the Bangle.js or eSense files using a method of your choice so that all files are assuming the same sampling rate (Hz).
	3. Watch the videos and write down the timestamps at which each activity happenend for which subject.
	4. Merge the all three files into one dataframe (Hint: you need to account for there not being records of all three sensors at all time since sensors were started/ stopped at 
	   different times).
	5. Apply the labeling obtained in step 3 to the dataframe you obtained (remember that there is also a null class!)
	6. Apply deep learning/ ML
	 
Starting and ending time of each activity:

	dribbling_sbj2_ts = {"Start": dt.timedelta(hours = 19, minutes = 27, seconds = 2, microseconds = 27),"End": dt.timedelta(hours = 19, minutes = 29, seconds = 55, microseconds = 30)}

	layup_sbj1_ts = {"Start": dt.timedelta(hours = 18, minutes = 23, seconds = 23, microseconds = 9),"End": dt.timedelta(hours = 18, minutes = 25, seconds = 23, microseconds = 26)}
	layup_sbj2_ts = {"Start": dt.timedelta(hours = 19, minutes = 17, seconds = 42, microseconds = 19),"End": dt.timedelta(hours = 19, minutes = 20, seconds = 8, microseconds = 37)}

	running_sbj1_ts = {"Start": dt.timedelta(hours = 18, minutes = 45, seconds = 18, microseconds = 69),"End": dt.timedelta(hours = 18, minutes = 47, seconds = 10, microseconds = 80)}
	running_sbj2_ts = {"Start": dt.timedelta(hours = 19, minutes = 39, seconds = 47, microseconds = 50),"End": dt.timedelta(hours = 19, minutes = 41, seconds = 49, microseconds = 81)}

	shooting_sbj1_ts = {"Start": dt.timedelta(hours = 18, minutes = 13, seconds = 31, microseconds = 40),"End": dt.timedelta(hours = 18, minutes = 15, seconds = 40, microseconds = 62)}
	shooting_sbj2_ts = {"Start": dt.timedelta(hours = 19, minutes = 0, seconds = 18, microseconds = 58),"End": dt.timedelta(hours = 19, minutes = 2, seconds = 4, microseconds = 35)}

	walking_sbj1_ts = {"Start": dt.timedelta(hours = 18, minutes = 42, seconds = 38, microseconds = 40),"End": dt.timedelta(hours = 18, minutes = 45, seconds = 16, microseconds = 45)}
	walking_sbj2_ts = {"Start": dt.timedelta(hours = 19, minutes = 37, seconds = 19, microseconds = 24),"End": dt.timedelta(hours = 19, minutes = 39, seconds = 45, microseconds = 82)}
