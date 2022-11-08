# 283-Assignment-1

1. Create GCP account and create project by enabling billing.
2. Once the project project is created enable cloud comptute engine API.
3. Now create virtual machine by using the below command and make sure to enable nested virtualization.

gcloud compute instances create instance-1 --project=virtualization-368001 --zone=us-central1-a --machine-type=n2-standard-8 --network-interface=network-tier=PREMIUM,subnet=default --maintenance-policy=MIGRATE --provisioning-model=STANDARD --service-account=810013729977-compute@developer.gserviceaccount.com --scopes=https://www.googleapis.com/auth/devstorage.read_only,https://www.googleapis.com/auth/logging.write,https://www.googleapis.com/auth/monitoring.write,https://www.googleapis.com/auth/servicecontrol,https://www.googleapis.com/auth/service.management.readonly,https://www.googleapis.com/auth/trace.append --tags=http-server,https-server --min-cpu-platform=Intel\ Cascade\ Lake --create-disk=auto-delete=yes,boot=yes,device-name=instance-1,image=projects/ubuntu-os-cloud/global/images/ubuntu-1804-bionic-v20221018,mode=rw,size=100,type=projects/virtualization-368001/zones/us-central1-a/diskTypes/pd-ssd --no-shielded-secure-boot --shielded-vtpm --shielded-integrity-monitoring --reservation-affinity=any --enable-nested-virtualization

4. Once an instance is created, open the instance using "gcloud compute ssh instance-1".
5. Make sure to include include all MSRs in the C file:
    1. Primary Process Based Controls (IA32_VMX_PROCBASED_CTLS)
    2. Secondary process based controls (IA32_VMX_PROCBASED_CTLS2)
    3. Secondary process based controls (IA32_VMX_PROCBASED_CTLS2)
    4. Entry controls (IA32_VMX_ENTRY_CTLS)
    5. Cannot include tertiary controls as it has Can set=No in primary controls
6. Install MAKE using the “apt install gcc make” command.
7. Check the Kernel version and install that version kernel version using "sudo apt-get linux-headers-$(uname -r)
8. Execute the "make" command to create the kernel object.
9. Now use "insmod cmpe283-1.ko command to load the kernel object.
10. Now, To see the output "dnesg" command.
<img width="1425" alt="Screen Shot 2022-11-07 at 6 24 10 PM" src="https://user-images.githubusercontent.com/55958864/200460212-c85453b9-c41c-46a8-b74c-c23006145379.png">
<img width="1437" alt="Screen Shot 2022-11-07 at 6 31 25 PM" src="https://user-images.githubusercontent.com/55958864/200460667-ea34a8e7-1e9c-496f-8271-1b894a5c7331.png">
<img width="1433" alt="Screen Shot 2022-11-07 at 6 32 20 PM" src="https://user-images.githubusercontent.com/55958864/200460795-190e6310-75c9-4981-b22c-7ff9acd0ed18.png">
