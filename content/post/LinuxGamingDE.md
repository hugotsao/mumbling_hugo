---
title: "LinuxGamingDE" # Title of the blog post.
date: 2023-04-30T17:42:27-04:00 # Date of post creation.
description: "Article description." # Description used for search engine.
featured: true # Sets if post is a featured post, making appear on the home page side bar.
draft: true # Sets whether to render this page. Draft of true will not be rendered.
toc: false # Controls if a table of contents should be generated for first-level links automatically.
# menu: main
usePageBundles: false # Set to true to group assets like images in the same folder as this post.
# featureImage: "/images/gamingDE.png" # Sets featured image on blog post.
#featureImageAlt: 'Description of image' # Alternative text for featured image.
featureImageCap: 'This is the featured image.' # Caption (optional).
thumbnail: "/images/gamingDE.png" # Sets thumbnail image appearing inside card on homepage.
shareImage: "/images/path/share.png" # Designate a separate image for social media sharing.
codeMaxLines: 10 # Override global value for how many lines within a code block before auto-collapsing.
codeLineNumbers: false # Override global value for showing of line numbers within code block.
figurePositionShow: true # Override global value for showing the figure label.
categories:
  - Technology
tags:
  - Linux_desktop_environment
  - Linux_gaming
# comment: false # Disable comment if false.

---
For years people criticize the resources Windows uses out of the box, and for years people in the Linux community praise how little Linux uses to run a system, but does it really matter when it comes to gaming? Let's find out.
Today I'm going to run some benchmarks on different desktop environments and compare them against each other so you can spend less time choosing and more time playing. The distribution I chose is nixOS. It is the perfect distribution to do so because changing the desktop on it is super easy, only 1 or 2 lines in the configuration file, and it will replace the entire desktop without leaving any traces, which means I can have a pure environment when running all the benchmarks.
And the games I'll be benchmarking are 2 legal copies of steam games, assassin's Creed origins, ACO in short, tomb raider, the first reboot in 2013, and red dead redemption 2, or RDR2 running in a bottle. Both steam and bottles are installed from flathub using flatpak, and you can find more details of why I do it this way in this video. As for the desktops, gnome and KDE will be using GDM and SDDM accordingly as it is the most common setup, and they will be running on wayland with only Assassin’s creed and RDR2. It is because I found that KDE Wayland performs much better in benchmarks compared to x11 when recording that video. The benchmarks of the red dead redemption 2 and ACO were actually not too far behind the stripped down gaming windows 10, I won’t run tomb raider on these 2 desktops because this game is 10 years old. I can’t start it using NVidia on wayland, the fps is around 32 with the integrated amd gpu inside the laptop. You could still use x11 instead if you want to play this game because even though the fps result is not as good as the window 10 on x11, it is still high enough to be more than playable as you will see later. The other desktops will be using lightdm and x11 combo.
### KDE
Let's start with KDE plasma on wayland. I am getting 32 minimum fps 67.3 maximum and 45.4 on average for red dead redemption 2. While on Assassin’s Creed Origins, it gave me a total fps of 8651 with 72 fps on average. The average fps is exactly the same as it is on Windows, and the overall frames are only 100 lower than windows. That is how good KDE is for running  games. The only issue is you can see 4 extreme glitches on Linux here, but it is clearly in the same league now.
### GNOME
On gnome. The results of Red Dead Redemption 2 are, minimum 25.4 fps, maximum 87.14 and average of 43 fps. It is almost identical to the benchmark I ran in the pure fedora with the same desktop environment, even though that is running through an USB 3.0 port on an external ssd.
Assassin’s Creed has an overall score of 8734 and the same 72 fps on average. Compared to KDE, the surprise is that I didn’t see any glitches while running the benchmark this time, and the score is higher, which is extremely impressive.
Now, we can see between the desktops that run on wayland, KDE is only slightly behind windows on both occasions, gnome has worse result on the RDR2 but almost matches the Windows score on Assassin’s creed. However, with less than 100 overall frame difference, I would say KDE and gnome are the same, because if I re-run this benchmark several times on both of them, they may end up averaging out. 
### XFCE
Let’s now go to xfce which is the default environment of Manjaro, one of the most famous gaming oriented distributions. Let's see if it makes sense. The result for RDR2 is very similar to the x11 KDE, with a dramatic range between 21.3 and 103.9. And the average is 45.18, which is worse than those on Wayland.
It’s the turn of Assassin’s creed. It has an overall frame rate of 8315 and achieved an average of  69 fps, the worst performer so far. Even the cpu and gpu speed were slower than the wayland desktops, however, I see only one or two tiny glitches this time, smoother than KDE. And tomb raider got 123 for its maximum, 78.6 for its minimum and 103.2 for average.
Clearly, it cannot match the performance to those wayland brothers, but let’s see if it can be the king in x11 category at least as we move on to cinnamon

### Cinnamon
Seems like the Manjaro team is onto something with xfce as their default, because the maximum frame rate of red dead redemption 2 on cinnamon is even higher, 107.8 and I’m getting a lower minimum of 18.6, while the average stays at 46.
Same story on The Assassin’s creed benchmark, it gave me an overall 7987 frames, with only 66fps on average, lowest so far with no glitch either. And the tomb raider had the result of maximum 124, minimum 77, and average 102, which is close to xfce, I guess it  makes less difference with old games like this on x11.
This is quite helpful if you want to choose between linux mint and ubuntu as your daily driver for gaming, because if we take out all the factors of modification and personal preference, gnome on wayland itself might be more attractive to gamers than cinnamon on Mint. But be mindful, I am using the pure gnome desktop on nixOS here, so you probably want to consider fedora over Ubuntu as Fedora has less modification of gnome out of the box.
### Pantheon
For some weird reason, mate is not loading up for me so I jumped over the pantheon, let’s see if the elementary os desktop environment can redeem for the x11. With RDR2, I got slightly better results than xfce and a little worse than gnome, with a maximum of 105, minimum of 22.7 and average of 46.4.
With no further expectations, I started Assassin’s creed, and holy moly, it reached 8874, highest score I’ve ever seen for this game. It is even higher than the Atlas score of 8766 by 1.2%, and I see no hiccups on the graphics during the benchmark at all. Even the average frame rate passed the highest I saw on gnome and Windows at 74. I’m gonna officially declare Linux gaming has passed Windows in performance right here right now. Well probably not yet, as in Tomb Raider, the benchmark reached top at 120 fps, 78.4 at lowest, and 100.6 for the average, which is still not as good as Windows.

### i3 and sway
I was thinking about adding i3 and sway into to this equation, but given the minimum setup nixOS needs for sway, I gave up, let me know in the comment below if you really really want to see that, I’ll consider it if I can get enough signals from you guys, but probably in some other times and distributions.

### Conclusion
Now based on what we have learned so far, if you only want to play older games from 10 years ago, you’d better stay with x11, because some of them don’t support wayland with nVidia, and it doesn’t matter which x11 environment you choose, they are all similar. The only disappointment I had was to see cinnamon had the lowest score of all, given how much and how long I have loved it. And if you want to play newer games, the safest bet is to use KDE on wayland. It will give you the stability and performance close enough to windows, but for some games, gnome can do a little bit better than KDE, while it is not as stable on the other hand. Finally, if you have to stay on x11, go with pantheon, even though it does not match the frame rates of Gnome in Red Dead Redemption, but it beats xfce, it has the best overall for Assassin’s Creed origins, including windows and can still play older games. True king in the x11 category. I know I also missed budgie, but there is no official support in nixos yet, so I had to postpone that into the future.

My original Youtube Video 

{{< youtube xolluhDi7Vc >}}