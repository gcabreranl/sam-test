# AI Writer 2.0 - Backend

New-gen **AI Writer** application on top of [Writesonic API](https://writesonic.com/api)

## Dependencies

    - Python 3.9

## Conventions

We format our python code using vanilla black. The command is the following (update excludes as needed):

        black . --exclude ".git|.idea"


## Local project setup 

1. Install [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/install-sam-cli.html)

    MAC:

        brew tap aws/tap
        brew install aws-sam-cli
    
2. Install [pipenv](https://pipenv.pypa.io)

        pip install --user pipenv

3. Create virtual environment using **Python 3.9** (the latest version supported by [AWS Lambda runtimes](https://docs.aws.amazon.com/lambda/latest/dg/lambda-runtimes.html))
        
        pipenv --python 3.9

4. Install dependencied and activate the virtual environment

        pipenv install
        pipenv shell  

5. Deploying

        sam build --use-container
        sam deploy --guided

6. Serve the AIWriter backend locally using an uvicorn worker
        
        uvicorn app.app:app --reload

    or

        pipenv run python app/app.py
