# eb tool Docker Image

[`eb`][eb] is the official command line interface for Elastic
Beanstalk.  This [Docker] image lets you install and use `eb` without
installing it or any of its dependencies natively.

## Usage

You'll need [Docker] installed to continue.

### Build

    docker build -t artburkart/eb .

### Configure

This container depends on IAM roles to function properly.
    
### Run

I'm only using this container for `eb deploy`

[eb]: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-getting-set-up.html
[Docker]: https://docs.docker.com/installation/
