# App Engine: 3 Ways: Challenge Lab || [ARC112](https://www.cloudskillsboost.google/course_templates/671/labs/407914) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

* ### Run the following Commands in CloudShell
```
export REGION=

export MESSAGE=""
```
```

# Set the ZONE variable
ZONE="$(gcloud compute instances list --project=$DEVSHELL_PROJECT_ID --format='value(ZONE)')"

# Enable the App Engine API
gcloud services enable appengine.googleapis.com


sleep 10
# SSH into the lab-setup instance and enable the App Engine API
gcloud compute ssh --zone "$ZONE" "lab-setup" --project "$DEVSHELL_PROJECT_ID" --quiet --command "gcloud services enable appengine.googleapis.com && git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
"

# Clone the sample repository
git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git

# Navigate to the hello_world directory
cd python-docs-samples/appengine/standard_python3/hello_world

# Update the main.py file with the message
sed -i "32c\    return \"$MESSAGE\"" main.py

# Check and update the REGION variable
if [ "$REGION" == "us-west" ]; then
  REGION="us-west1"
fi

# Create the App Engine app with the specified service account and region
gcloud app create --service-account=$DEVSHELL_PROJECT_ID@$DEVSHELL_PROJECT_ID.iam.gserviceaccount.com --region=$REGION

# Deploy the App Engine app
gcloud app deploy --quiet


gcloud compute ssh --zone "$ZONE" "lab-setup" --project "$DEVSHELL_PROJECT_ID" --quiet --command "gcloud services enable appengine.googleapis.com && git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
"
```

# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
