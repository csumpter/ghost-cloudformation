# Overview

These cloudformation templates enable you to deploy a highly availbile ghost blog with RDS and utilizing S3 as the backend static content store.

## Deployment instructions

* Code is written in AWS cloudformation templates with yaml formatting
* Do the following:
  * clone the repo to a local dir `git clone git@github.com:csumpter/ops-challenge.git`
  * Create a __public__ S3 bucket on your aws account
  * open master.yaml on your computer in an editor of choice
    * change any reference to `TemplateURL: https://s3.amazonaws.com/ghost-service/.../<file name here>.yaml` to `TemplateURL: https://s3.amazonaws.com/<your bucket name>/.../<file name here>.yaml`
  * Upload the modified dir and all of its contents to the AWS S3 bucket.
  * Copy the S3 url of the master.yaml file. It should be `https://s3.amazonaws.com/< your bucket name>/master.yaml`
  * Take that url and go to the AWS console - Under 'Management Tools' go to - 'CloudFormation'
  * Click 'Create Stack'
  * Choose 'Specify an Amazon S3 template URL'
  * Paste your S3 master.yaml url
  * Click 'Next'
  * Provide a 'Stack Name'
  * Provide a 'DatabasePassword'
     * Other parameters are optional and prefilled
  * Click 'Next'
  * Click 'Next' again to go to the final setup page.
  * Check the box at the bottom 'I acknowledge that AWS CloudFormation might create IAM resources with custom names.'
  * Click 'Create'

  Your stack will now be created. This takes about 20-25 minutes under the current build.