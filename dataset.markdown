<h1>About the dataset</h1>
The combined measurement datasets including the `ssd` and `nic_2` folders for all the samples are in the attached zip file. Measurements for all the samples were collected with the FakeNet-NG configuration instead of using a mobile phone that allows the malware samples to directly connect to the internet. The directory structures and time settings are as before and are detailed below. For all the malware samples, the data collection is started when the VM is launched. The malware sample is
launched at t=400 s. At 700 s, an attempt is made to kill the original malware process that was started. For several malware, the original malware process could start other processes and/or infiltrate the kernel via a rootkit in which case the operation would continue even after the kill command is issued to terminate the original launched malware process. The data collection is continued until t=820 s.

<h2>Syscall Trace<h2>
