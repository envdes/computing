## CSF Tips 

### Log in

**Windows Users**

Use MobaXterm ([link](https://ri.itservices.manchester.ac.uk/csf3/getting-started/connecting/windows/))

**On-campus Access (Off-campus Access via the GlobalProtect VPN)** 

```bash
ssh username@csf3.itservices.manchester.ac.uk
```

**Use CSF IP numbers directly (if the above hostname doesn't work)**

```bash
ssh username@10.99.203.51
# OR
ssh username@10.99.203.52
```

**Access to External Websites and Repositories from the CSF** ([link](https://ri.itservices.manchester.ac.uk/csf3/software/tools/proxy/))

Before running git, use (interactive session)[https://ri.itservices.manchester.ac.uk/csf3/batch-slurm/srun/]:

```bash
srun -p interactive -n 4 -t 0-1 --pty bash
```

You will then be able to clone from http(s) repositories. For example:

```bash
git clone https://github.com/myproject.git myproj
```

**Check your primary group (the first listed) plus any secondary groups** ([link](https://ri.itservices.manchester.ac.uk/csf3/faqs/user-faq/))

```bash
groups
```
