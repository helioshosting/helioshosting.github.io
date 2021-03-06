---
layout: post
title: Basic Build Outline
published: true
---

#### Foreword
Like many others I came across this [site](https://amc.ovh/ "Automated Media Center") and was immediately intrigued by the idea of a Plex server based on unlimited cloud storage. So I did the rational thing and I immediately purchased a cheap VPS. After quite a few hours of trial and error and reading many different guides, I had the "Infinite" Plex server up and running. I chose to use rclone rather than the acd_cli-EncFS combination, which did make the process somewhat simpler. However the performance was less than ideal, media took too long to start playing and seeking was completely broken. The mount would also go stale and Plex would not see any new media until I went through the unmount and remount process. And so I began my search for a more functional method for an encrypted cloud based Plex media server and that is how I discovered CloudDrive.    
     
      
>Note: CloudDrive is not a free product, there is a one time cost of $35 (There is a free 30-day evaluation period). I am not affiliated with CoveGube and I am only recommending their product because it meets and exceeds my expectations and requirements.  

#### General Overview
I have this setup currently working on a dedicated server from Online.net, but it should work on any VPS running a new enough version of Windows. This setup avoids the mess that is Fuse and instead relies on a piece of software from CoveCube called CloudDrive. CloudDrive has built in AES-256 kernel-based encryption, predictive prefetching, and a resizable local cache among other features that work great for streaming. This setup process is surprisingly simple and only requires Plex, StableBit CloudDrive, and a supported cloud storage provider. As of now the supported cloud storage providers are Amazon S3, Box, Dropbox, Google Cloud Storage, Google Drive, Microsoft Azure Storage, OneDrive, OneDrive for Business and the latest beta includes support for Amazon Cloud Drive and can be found [here.](http://dl.covecube.com/CloudDriveWindows/beta/download/?C=M;O=D) I recommend Amazon Unlimited Cloud Drive because of it's low price and exceptional speed. I have also succesfully used Google drive.
Main requirements:
    
* Supported Cloud Storage Provider (I have tried both Amazon cloud drive and Google drive)
* Server or Computer Running Windows (I use Windows server 2012)
* StableBit CloudDrive, latest beta [here.](http://dl.covecube.com/CloudDriveWindows/beta/download/?C=M;O=D)

>Note: The latest beta requires you to have an Amazon developer account to use Amazon cloud drive, while this is free, you can also download the 631 beta from [here](http://dl.covecube.com/CloudDriveWindows/beta/download/) and avoid making a developer account. If Amazon Cloud Drive does not show up make sure you enable experimental providers in the settings.    
     
#### Quick Setup Instructions
Simply download CloudDrive and follow the steps to setup and mount your cloud storage as a local drive make sure to check the encryption option if you want to encrypt your data stored on the cloud (recommended). I chose to make my drive 100TB paired with a local cache of 50GB. This ensures that my most watched content stays quickly accessible. Now just add your content to the mounted drive and point Plex to it. It really is that simple. I use FileBot to automatically sort and then hard-link my media from my downloaded folder to the mounted cloud drive. CloudDrive will then automatically encrypt and upload the media. The only negative with the combination of CloudDrive and Plex is that the initial scan of my media seems to be quite slow.
     
>Note: It has recently come to my attention that Amazon cloud drive seems to be throttling CloudDrive users quite heavly so as of now I would reccomend Google drive unlimited. I also recommend backing up your data elsewhere to ensure you are no entirely dependent on StableBit. Backing up your data in the same cloud drive outside of the StableBit folder would probably suffice. I use rclone for this.

>Final Note: Several people have asked me for the recommended CloudDrive settings. The reason I didn't recommened any settings is that I believe it to be highly dependent on a number of variables that will differ for each user depending on their setup enviorment. I also would just like to point out that unlimited Google drive accounts can be purchased on eBay for as low as $10, Microsoft license keys can be purchased cheaply [on reddit.](reddit.com/r/MicrosoftSoftwareSwap) Buy at your own risk. I cannot guarantee anything. Make sure you do your own research.