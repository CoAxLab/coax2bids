## Physiological Data Labeling: 


  1)Events file 
    sub-##[_ses-<sesion_label>]_task-<task_name>[_recording-<label>]_physio.tsv.gz
    
    Example: *sub-0006_ses-1_task-Prostop_physio.tsv.gz*
    
  2) Metadata 
  
  
    sub-##[_ses-<sesion_label>]_task-<task_name>_events.json 
    
    Example: *sub-0006_ses-1_task-Prostop_events.json*
    
Physiological recordings such as cardiac and respiratory signals and other continuous measures (such as
parameters of a film or audio stimuli) can be specified using two files: a gzip compressed TSV file with data
(without header line) and a JSON for storing start time, sampling frequency, and name of the columns from the TSV.
Please note that in contrast to other TSV files this one does not include a header line. Instead the name of columns
are specified in the JSON file. This is to improve compatibility with existing software (FSL PNM) as well as make
support for other file formats possible in the future. Start time should be expressed in seconds in relation to the time
of start of acquisition of the first volume in the corresponding imaging file (negative values are allowed). Sampling
frequency should be expressed in Hz. Recordings with different sampling frequencies and/or starting times should
be stored in separate files. The following naming conventions should be used for column names:


● cardiac: continuous pulse measurement

● respiratory: continuous breathing measurement

● trigger: continuous measurement of the scanner trigger signal


Any combination of those three can be included as well as any other stimuli related continuous variables (such as
low level image properties in a video watching paradigm).

Physiological recordings (including eye tracking) should use the _physio suffix, and signals related to the
stimulus should use _stim suffix. For motion parameters acquired from scanner side motion correction please use
_physio suffix.


More than one continuous recording file can be included (with different sampling frequencies). In such case use
different labels. For example: _recording-contrast, _recording-saturation. The full file name could
then look like this: sub-control01_task-nback_run-2_recording-movie_stim.tsv.gz


For multi-echo data, physio.tsv file is applicable to all echos of particular run.

For eg:

sub-01_task-cuedSGT_run-1_physio.tsv.gz

sub-01_task-cuedSGT_run-1_echo-1_bold.nii.gz

sub-01_task-cuedSGT_run-1_echo-2_bold.nii.gz

sub-01_task-cuedSGT_run-1_echo-3_bold.nii.gz
