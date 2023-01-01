## CSF Tips 

### Log in

**Windows Users**

Use MobaXterm ([link](https://ri.itservices.manchester.ac.uk/csf3/getting-started/connecting/windows/))

**On-campus Access**

```bash
ssh username@csf3.itservices.manchester.ac.uk
```

**Off-campus Access via the GlobalProtect VPN**

```bash
ssh username@10.99.203.51
# OR
ssh username@10.99.203.52
```

**Access to External Websites and Repositories from the CSF** ([link](https://ri.itservices.manchester.ac.uk/gateways-and-proxies/web-proxy/))

Before running git, set the following in your environment:

```
export HTTP_PROXY=http://proxy.man.ac.uk:3128
export HTTPS_PROXY=$HTTP_PROXY
```

You will then be able to clone from http(s) repositories. For example:

```
git clone https://github.com/myproject.git myproj
```





