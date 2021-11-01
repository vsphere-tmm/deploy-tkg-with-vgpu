# deploy-tkg-with-vgpu
the code repo for TKG vgpu deployment/operations guide

this repo includes two sub directories
1. vSphere TKG Cluster definition YAML files
tkg-cluster-with-vgpu/
- tkc-single-gpu-vmxnet3.yaml: to create 2 worker nodes each with the identical single vgpu configured.
- tkc-single-gpu-passthru-nic.yaml: to create 2 worker nodes each with the identical single vgpu and passthru nic configured.
- tkc-mixed-gpu-vmxnet3.yaml: to create 2 worker nodes with a100 vgpu and 2 worker nodes with v100 vgpu configured.
- tkc-mixed-gpu-passthru-nic.yaml: to create 2 worker nodes with a100 vgpu and passthru nic; 2 worker nodes with v100 vgpu and passthru nic configured.

2. vSphere TKG Stand-alone VM definition YAML files
stand-alone-vm-with-vgpu/
- stand-alone-vm-with-vgpu.yaml: to create one VM with single vgpu configured.
- stand-alone-vm-with-vgpu-passthru-nic.yaml: to create one VM with single vgpu and passthru nic configured.
- user-data.yaml: the user-data of the VM service, should be encoded by "cat user-data.yaml | base64 -w 0" and paste the output as the value of "user-data" in those 2 YAML files above.
