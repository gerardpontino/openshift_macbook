Testing OpenShift locally on a Mac with these powerful processors can be a fast and efficient way to start learning about OpenShift. In this guide, I will walk you through the process of setting up OpenShift on your Mac and also deploy and test your first web app. By leveraging tools compatible with ARM architecture, you’ll quickly gain hands-on experience and accelerate your learning process.

Before we begin, you’ll need to get a few things in place:

### 1. Register a Red Hat Account

- The first step in getting started with OpenShift is to create a personal Red Hat account. This account is necessary for downloading certain Red Hat tools, such as CodeReady Containers (CRC), which we’ll be using later.
- Go to the [Red Hat Registration page](https://access.redhat.com/?source=post_page-----73900e6d26ad--------------------------------) and fill in your details. Make sure to verify your email address after registering.

### 2. Access the OpenShift Console

- After registering, go to https://console.redhat.com/openshift/ in your browser and follow the below steps.
- Navigate to the Cluster List section.
- Click on Create Cluster.

![01](https://github.com/user-attachments/assets/43876fd1-8706-48f0-ab79-39151f4725cc)

- Select the Local tab.
- Choose MacOS as your platform.
- Download the OpenShift Local installer for Mac.

**Important**: In this window, click on “Copy Pull Secret.” You’ll need this later when setting up CRC in Step 3.


- Launch the downloaded installer to install the Red Hat OpenShift Local.

### 3. Open the Terminal application on your mac and run the following command to set up CRC:

```bash
crc setup
```


After the setup is complete, start the OpenShift Local cluster by running:

```bash
crc start
```

During this step, you will be prompted to enter the pull secret. This is the pull secret you copied earlier in Step 2. Paste it when prompted to continue with the cluster setup.


Once the OpenShift cluster starts, the terminal will display the URL for accessing the web console. It will also provide the credentials for both the admin and developer accounts.


### 4. Access the Openshift Web Console

Attempt to log in using the credentials provided. You can use either the admin credentials (kubeadmin) or the developer credentials. Verify that you can successfully access the OpenShift web console with both sets of credentials.


Once logged in successfully, you should see the OpenShift web console dashboard. Below is a sample screenshot of the page for reference:

### 5. Using OpenShift CLI (oc) in your local terminal

The OpenShift CLI (oc) is essential for interacting with your OpenShift cluster from the command line. Here’s how to install it:

In the Openshift web console, click on the “?” icon on the upper right of page, then select Command Line Tools.


Select Download oc for Mac for ARM 64

### 6. Authenticate to the Openshift environment.

In the upper right, click the username and select Copy login command from the drop down.

Copy the login command with the token.

Paste the login command in the terminal to log into the environment.

## Deploying your first test Application
In this example, we will be using this sample from github https://github.com/mosuke5/microservices-demo-openshift=

Clone the project and deploy ``complete-demo.yaml``

```bash
╭─   ~/Documents/Work/study/openshift ················································································  11:57:32 AM
╰─❯ git clone https://github.com/mosuke5/microservices-demo-openshift.git
Cloning into 'microservices-demo-openshift'...
remote: Enumerating objects: 142, done.
remote: Counting objects: 100% (51/51), done.
remote: Compressing objects: 100% (24/24), done.
remote: Total 142 (delta 39), reused 27 (delta 27), pack-reused 91 (from 1)
Receiving objects: 100% (142/142), 4.44 MiB | 1.99 MiB/s, done.
Resolving deltas: 100% (61/61), done.
```

#### Open the OpenShift Console:

Navigate to the OpenShift web console at the URL you obtained earlier.
Check the status of your deployments to ensure that they are running correctly. Look for the application you deployed and verify that the pods are up and running.

#### Locate the Application Route:

In the OpenShift console, go to the Networking section and click on Routes.
Find the route for the front-end application in the list.
Copy the URL provided under the Location column. This URL will be used to access the front-end application.

#### Access the Application:

Open your web browser and paste the copied URL to access the deployed application.

...

## Key Takeaways
In this example, we’ve demonstrated how straightforward it is to install OpenShift Local on a Mac with an M series chip. Setting up a local OpenShift environment allows you to:

Quickly Get Started: With OpenShift Local, you can set up a fully functional OpenShift cluster on your local machine with minimal effort.
Experiment and Learn: It provides a convenient platform for learning OpenShift and experimenting with its features without needing a cloud-based cluster.
Explore Use Cases: Once installed, you can deploy applications, test configurations, and explore various use cases directly on your local machine.
This setup is particularly useful for developers and IT professionals who want to familiarize themselves with OpenShift, develop and test applications, or prepare for more advanced deployments. With OpenShift Local, you have a powerful tool at your fingertips for hands-on learning and development.
