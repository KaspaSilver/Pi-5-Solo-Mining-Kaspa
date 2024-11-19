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
+ Learn to download Git
+ Learn to download the kaspa-stratum-bridge
+ Learn to download Kaspa-NG


# Step 1: Downloading GO
+ Head over to https://go.dev/dl/
+ Download the latest Linux version that has the ending as **arm64.tar.gz**

Open your terminal and go to your downloads directory by pasting this command

```
cd Downloads
```

Next, check to make sure you have the file by pasting this command

```
ls -lh
```

It should show you the file you just downloaded within your download directory

Now, let's unpack the file with this command

```
sudo tar -C /usr/local -xzf go1.xx.x.linux-arm64.tar.gz
```
Note: Replace go1.xx.x.linux-arm64.tar.gz with the actual filename of the Go tarball you downloaded.

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
export PATH="$PATH:/usr/loc/go/bin"
```
Save what you just entered by clicking CTRL + S
Restart your Pi Device

Go into your terminal again and enter this command
```
go version
```
You should see a version which means you have succsfully installed Go!

# Step 2: Download Rust

Open your terminal and run these commands to update your system
 (May take 5-10min)
```
sudo apt update
sudo apt upgrade
```

Install dependencies with this command
```
sudo apt install curl build-essential
```
Install Rust with this command
  (May take 5-10min)
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Then verify the install with this command
```
rustc --version
```
You should see a version which means you have succsfully installed Rust!

# Step 3: Download Git

Run this command to download
```
sudo apt install git
```
Verify install with this command
```
git --version
```
You should see a version which means you have succsfully installed Git!

# Step 4: Download Kaspa-Stratum-Bridge
Now because some users do have goldshell miners we will be downloading the bridge under the goldshell branch to ensure the bridge works with all miners. Please make sure your miners are updated to the latest version as well.

Lets clone the repository for goldshell
```
git clone https://github.com/rdugan/kaspa-stratum-bridge.git
```
Next, Cd into the kaspa-stratum-bridge
```
cd kaspa-stratum-bridge
```

Then ensure you are on goldshell branch by running this command
```
git checkout goldshell
```
Next enter this command
```
cd cmd/kaspabridge
```

Build with this command next
```
go build
```

Start the bridge with this command
```
./kaspabridge
```
The bridge should start!

**Note: Make sure you change local host to 127.0.0.1 in the config file and if you are using a goldshell device set the extranonce_size to 3**

# Step 5: Download Kaspa-NG

Open a fresh terminal and run this command
```
git clone https://github.com/aspectron/kaspa-ng.git
```

Build Kaspa-NG (About 35min)
```
cd kaspa-ng
cargo build --release
```
After it builds run it with this command
```
./target/release/kaspa-ng
```

After that, you are done! For configuration setup check out this video I made: [How To Solo Mine To Your Own Node Using KNG On Kaspa
](https://youtu.be/2MuebQia1F0?si=ZzxXJgSGUnddRTs8)

If you wanna support my work consider donating: kaspa:qpshhxee9q9ej5qz9x4rxe6708h3735lh9q9qv593yefxvk75fcm26xvdrwfw
