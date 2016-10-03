---
layout: post
title: Basic Build Outline
---
>Note: CloudDrive is not a free prodcut, there is a one time cost of $35 (There is a free 30-day evaluation period)

##General Overview
I have this setup currently working on a dedicated server from Online.net, but it should work on any VPS running a new enough version of Windows. This setup avoids the mess that is Fuse and instead relies on a piece of software from CoveCube called CloudDrive. CloudDrive has built in AES-256 kernel-based ecryption, predictive prefetching, and a resizable local cache among other features that make work great for streaming. This setup process is surprsingly simple and only requires Plex, StableBit CloudDrive, and a supported cloud storage provider. As of now the supported cloud storage providers are Amazon S3, Box, Dropbox, Google Cloud Storage, Google Drive, Microsoft Azure Storage, OneDrive, OneDrive for Business and the latest beta includes support for Amazon Cloud Drive and can be [here.](http://dl.covecube.com/CloudDriveWindows/beta/download/?C=M;O=D). I reccomend Amazon Unlimited Cloud Drive because of it's low price and exceptional speed.
Main requirements:
    
* Supported Cloud Storage Provider
* Server or Computer Running Windows
* StableBit CloudDrive   
     
##Quick Setup Instructions:
Simply download CloudDrive and follow the steps to setup and mount your cloud storage as a local drive make sure to check the encryption option if you want to encrypt your data stored on the cloud (recommended). I chose to make my drive 100TB paired with a local cache of 50GB. This ensures that my most watched content stays quickly accesible. Now just add your content to the mounted drive and point Plex to it. It really is that simple. I use FileBot to automatically sort and then hardlink my media from my downloaded folder to the mounted cloud drive. CloudDrive will then automatically encrypt and upload the media. The only negative with the commbination of CloudDrive and Plex is that the initial scan of my media seems to be quite slow. 
