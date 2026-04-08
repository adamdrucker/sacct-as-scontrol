# sacct-as-scontrol

Have you ever cursed at `sacct` in Slurm, and lamented about having to decipher the output using `--parsable`?

Do you ever find yourself wishing that `sacct` output for historical jobs could be more like what `scontrol` shows for active jobs?

Maybe `srecall` can help you.

## Info
`srecall` pulls historical job information for a specific job ID and formats it like you would see from `scontrol`. 

## Usage
~~~
./srecall <job-id>
~~~

## Example
~~~
[root@admin002 bin]# srecall 11547368
JobId=11547361_1 JobName=test10aug
   UserId=ageod GroupId=general MCS_label=N/A
   Priority=266817 Nice=0 Account=general QOS=normal
   JobState=FAILED Reason=None Dependency=(null)
   TimeLimit=01:00:00 SubmitTime=2026-04-08T14:17:46 EligibleTime=2026-04-08T14:17:47
   StartTime=2026-04-08T14:18:02 EndTime=2026-04-08T14:18:03 Deadline=N/A
   SuspendTime=None SecsPreSuspend=0
   Partition=normal AllocNode:Sid=N/A:0
   ReqNodeList=0.00M ExcNodeList=(null)
   NodeList=node1608
   NumNodes=1 NumCPUs=1 NumTasks=0 TRES=billing=1,cpu=1,mem=4096M,node=1
   ReqTRES=billing=1,cpu=1,mem=4096M,node=1
   Socks/Node=* NtasksPerN:B:S:C=0:0:*:* CoreSpec=*
   MinCPUsNode=1 MinMemoryNode=4096M MinTmpDiskNode=0
   Features=(null) DelayBoot=00:00:00
   OverSubscribe=OK Contiguous=0 Licenses=(null) Network=(null)
   Command=test10aug
   WorkDir=/work/home/002/ageod
   StdErr=(null)
   StdIn=/dev/null
   StdOut=/work/home/002/ageod/testing_%j.out
   Power=
   ArrayJobId=11547361 ArrayTaskId=1
   Constraints=(null) Flags=SchedBackfill,StartReceived Restarts=0
   ExitCode=127:0 DerivedExitCode=0:0
   Comment=(null)
   Cluster=eofe7
   Duration=00:00:01 CPUTime=00:00:01 TimeLimit=01:00:00 TimelimitSecs=3600
   MaxRSS=N/A MaxVMSize=N/A
~~~

## Credits
<sub>Co-authored by Claude</sub>
