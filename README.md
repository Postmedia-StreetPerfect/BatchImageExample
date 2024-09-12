# BatchImageExample

The StreetPerfect public batch Docker images contain the latest (monthly) Canada Post data as well as the latest StreetPerfect batch applications.

To test the image, all that is required to run is a StreetPerfect license key.  You can set the license in a config INI file or pass it via environment as SP_UserLicenseKey.

    docker run -it --name sp-batch-run -e SP_UserLicenseKey=[your-key]  public.ecr.aws/postmedia/streetperfect/sp-poc-batch-public 

Typically you would point a volume to a folder on your system that contains your CSV input data and a StreetPerfect INI settings file.

    docker run -it --name sp-batch-run  -v /mydata:/spdata   public.ecr.aws/postmedia/streetperfect/sp-poc-batch-public  /spdata/MyDockerSpPoc.ini

	or from windows commandline:
	docker run -it --name sp-batch-run  -v c:\mydata:/spdata   public.ecr.aws/postmedia/streetperfect/sp-poc-batch-public  /spdata/MyDockerSpPoc.ini

Where /mydata contains your input file and INI file.

A better way to run these batch images - in a cloud environment - is to create your own Dockerfile and have a CICD pipeline re-build your image each month.  An example Dockerfile and an AWS cloudbuild yml spec file is provided in this repo.

