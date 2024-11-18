# How To Solo Mine Kaspa With A Raspberry Pi 5
**Complete guide on how to solo mine Kaspa with a Raspberry Pi 5**

# **What you will need:**

+ [Raspberry Pi 5 by CanaKit](https://www.amazon.com/CanaKit-Raspberry-Starter-Kit-PRO/dp/B0CRSNCJ6Y/ref=sr_1_2_sspa?crid=3TUDNJIT2R4ZD&dib=eyJ2IjoiMSJ9.u2oDKCJT68HpfRt_WkmjCl6bbz7mK8GylxKu8hDxrb-VmtApJLOyzMvH_9RPRzAL6nM9CnYkiIndRS_qTHXAgd4CCU0-hDEMNZpItia7fmBJXqW9EM_fKKk-BZVpCj1N07xCw74D64M4_ZpVhVGCaclJarJUitQ8mgA08gVZJeG2uEIsXUkaO4bBT3x71koCcKlRyjv5Ip3zjemQZe_Bsu4wL8zSH37FpMUzJ0oFtWA.aBOaY1QCZ_C-PIpZtS8yR1_Zh1tJINWE-1zXl6b1We4&dib_tag=se&keywords=raspberry%2Bpi%2B5%2B8gb&qid=1731960836&sprefix=ras%2Caps%2C155&sr=8-2-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)
 (You don't have to buy this version but this comes with everything and is the one I purchased)
+ There is a good video [here](https://www.youtube.com/watch?v=Wi_S7QkuN3M) that shows you how to setup the Pi 5 after receiving it.
+ An ASIC that mines kheavyhash

# **What you will learn to do:**
+ Learn to download GO
+ Learn to download Rust
+ Learn to download the kaspa-stratum-bridge
+ Learn to download Kaspa-NG


# Step 1: Downloading GO
+ Head over to https://go.dev/dl/
+ Download the latest Linux version that has the ending as **arm64.tar.gz**

Open your terminal and go to your downloads directory by pasting this command

```
cd downloads
```

Next, check to make sure you have the file by pasting this command

```
ls -lh
```

It should show you the file you just downloaded within your download directory

Now, let's unpack the file with this command

```
sudo tar -C /usr/local -xzf [Entire filename you just downloaded here]
```

After you unpack the file enter this command
```
ls /usr/local/go/
```

You should get something like this 

![image](https://github.com/user-attachments/assets/8b821b32-2f11-465f-908b-bebc7f8192ee)

Next, paste this command so that you can run the go command
```
ls /usr/local/go/bin
```
This should return "go gofmt"

Then paste this command
```
nano ~/.profile
```

This will bring you to a new screen within the terminal that you can then scroll down to the very bottom until you see this

<img width="721" alt="Screenshot 2024-11-18 170537" src="https://github.com/user-attachments/assets/30e56cba-23e4-462c-acaa-7f100b0e6704">

Where the blue arrow is copy and paste this command
```
export= PATH="$PATH:/usr/loc/go/bin"
```
Save what you just entered by clicking CTRL + O
Restart your Pi Device

Go into your terminal again and enter this command
```
go version
```

You should see a go version appear

Congratulations you have downloaded GO to your device!

# Step 2 Download Rust
