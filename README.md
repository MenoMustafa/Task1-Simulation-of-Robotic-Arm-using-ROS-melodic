<h1>Simulation of Robotic Arm using ROS melodic</h1>


<h2>Setup ROS Melodic Environment on Ubuntu.</h2>
<p>To install robotic arm package, we need to set up the development environment of ROS melodic on</p> 
<p>Ubuntu 18.04, which had installed on Windows 10 using VirtualBox.<p>
 <p> Set up the computer to accept software from packages.ros.org, we write this command:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'</code></pre></div>
<p> Set up the public key to make sure we use the authentic ROS Melodic: </p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654</code></pre></div>
<p> Here, we need to make sure the Debian package is up-to-date:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt update</code></pre></div>
<p> The actual installation of ROS, install all the important ROS libraries via the following command. When prompted, write “y” to continue the installation:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt install ros-melodic-desktop-full</code></pre></div>
<p> To get the available packages:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>apt search ros-melodic</code></pre></div>
<p> ROS environment variables have automatically added to the bash session whenever the new shell is launched:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc </code></pre></div>
<p> Rosinstall is a tool in ROS used to download multiple source trees for ROS packages with one command. To install rosinstall and other</p>
<p> dependencies for building ROS packages. In a Terminal window, type:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool
build-essential</code></pre></div>
<p> To install rosdep, which is a tool used to install the system dependencies for the source code we want to compile, run:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt install python-rosdep</code></pre></div>
<p> Rosdep is a required tool to run some important components in ROS. To initialize rosdep:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo rosdep init</code>
rosdep update</pre></div>
<p> To install and build catkin: </p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt-get install ros-melodic-catkin</code></pre></div>
<p> To create a catkin workspace: </p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/</code></pre></div>
<p> To create directories in a catkin workspace, run:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>catkin_make</code></pre></div>
<h2>Install The Robotic Arm Package.</h2>
<p> Change the directory to src. To enable making a copy of the targeted repository for the robotic arm, run:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>cd ~/catkin_ws/src
git clone https://github.com/smart-methods/arduino_robot_arm.git</code></pre></div>
<p> After changing the directory into catkin_ws, then run this command inside the workspace:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y</code></pre></div>
<p> To install all these packages for melodic distribution, run</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo apt-get install ros-melodic-moveit
sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control</code></pre></div>
<p> To run the commands that we want to run every time we open a shell:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>sudo nano ~/.bashrc
(source /home/meno21/catkin_ws/devel/setup.bash)</code></pre></div>
<p> To update bashrc file, run: </p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>source ~/.bashrc</code></pre></div>
<p> Run the following command to control the robotic arm using Rviz:</p>
<div class="snippet-clipboard-content position-relative" data-snippet-clipboard-copy-content="  Number of colours/ shades = 2^bpp where bpp represents bits per pixel.
"><pre><code>roslaunch robot_arm_pkg check_motors.launch</code></pre></div>
<img src="/Images/robot_arm.png" width="350" height="350">
