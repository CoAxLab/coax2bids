## Behavioral Data Labeling: 


  1)Events file 
    sub-##[_ses-<sesion_label>]_task-<task_name>_events.tsv
    
    Example: *sub-0006_ses-1_task-Prostop_events.tsv*
    
  2) Metadata 
  
  
    sub-##[_ses-<sesion_label>]_task-<task_name>_events.json 
    
    Example: *sub-0006_ses-1_task-Prostop_events.json*
    
    
    
Files that don't include onset and duration columns should be in a separate file named _beh.tsv instead of _events.tsv



The purpose of this file is to describe timing and other events recorded. Events may be **either** stimuli presented to the participant or participant responses. A single event file may include a combination of stimuli and response events.

| Column Name  | Description |
| ------------- | ------------- |
| onset  | **Required** Onset (in seconds) of the event measured from the beginning of the task.  |
| duration  | **Required** Duration of the event (measured from onset) in seconds. Must always be zero or position. A duration value of zero implies that the delta function or event is so short as to be effectively modeled as an impulse.   |
| trial_type  | **Optional** Primary categorization of each trial to idenity them as instances of the experimental conditions. For example: a response inhibition task could take on values "go" and "no-go" to refer to response initiation and response inhibition experimental conditions.  |
| response_time  | **Optional** Response time measures in seconds. A negative response time can be used to represent preemptive responses and "n/a" denotes a missed response.   |
| stim_file  | **Optional** Represents the location of the stimulus file (image, video, sound, etc) presented at the given onset time. There are no restrictions on the file formats of the stimuli files, should be stores in the /stimuli folder (root directory of the dataset). The values under the stim_file column correspond to a path relative to /stimuli. Ex: /stimuli/images/cat03.jpg  |
| HED  | **Optional** Hierarchical Event Descriptor (HED)  |




Json files include any relevant metadata you think is necessary for a better understanding see examples. 
