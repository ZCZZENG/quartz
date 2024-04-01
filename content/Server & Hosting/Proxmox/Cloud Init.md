---
publish: "true"
---
get image from cloud ubuntu

`qm create 800 --memory 2048 --name ubuntu-cloud -net0 virtio,bridge=vmbr1`

`qm importdisk 800 jammy-server-cloudimg-amd64-disk-kvm.img  local`

`qm set 800 --scsihw virtio-scsi-pci --scsi0 local:800/vm-800-disk-0.raw`

`qm set 800 --ide2 local:cloudinit`

`qm set 800 --boot c --bootdisk scsi0`

`qm set 800 --serial0 socket --vga serial0`
