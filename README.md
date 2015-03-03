# eb tool Docker Image

[`eb`][eb] is the official command line interface for Elastic
Beanstalk.  This [Docker] image lets you install and use `eb` without
installing it or any of its dependencies natively.

## Usage

You'll need [Docker] installed to continue.

### Build

    docker build -t adzerk/eb .

### Configure

    docker run -i -t adzerk/eb bash
    # eb init -r us-east 1

After entering your AWS credentials, and while the container is
running, and in a separate termainal, commit the container's
filesystem:

    docker commit -m 'add eb credentials' <container-id> adzerk/eb

Then, `exit` the running container.
    
### Run

Navigate to a Beanstalk project directory.  Then, to e.g. SSH to a Beanstalk instance:

    docker run -v $PWD:/app -v <dir-with-pems>:/root/.ssh -i -t adzerk/eb eb ssh

Substitute `<dir-with-pems>` for some directory containing your `.pem` files.

You may alias this invocation to `eb`:

    alias eb='docker run -v $PWD:/app -v <dir-with-pems>:/root/.ssh -i -t adzerk/eb eb'

Then, you can run `eb` commands easily:

    eb list
    eb events

[eb]: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-getting-set-up.html
[Docker]: https://docs.docker.com/installation/