# CVEServer

Simple REST-style web service for the CVE searching.

## Requirements

  * [Ruby Version Manager](https://rvm.io)
  * [Ruby 2.4.x or later version](https://www.ruby-lang.org)
  * [Bundler](https://bundler.io)
  * [Mongo DB](https://www.mongodb.org)

## Getting Started

### Install the CVE Server

You must have running ruby, git, mongodb and nginx in your local machine.

```
curl --ssl -s https://raw.githubusercontent.com/SpiderLabs/cve_server/master/scripts/install.sh | bash -
```

## Using the API

* Search for an specific CVE using its ID

  * http://localhost:port/v1/cve/CVE-2015-3900

* Search for several CVEs

  * http://localhost:port/v1/cves/CVE-2019-14407,CVE-2018-18656

* Search for CVEs related to a CPE without versions

  * http://localhost:port/v1/cpe/apache:spark

  * http://localhost:port/v1/cpe/apache:spark,apache:http_server

* List all the available CPEs with versions

  * http://localhost:port/v1/cpe

* Search for CVEs related to a CPE with versions

  * http://localhost:port/v1/cpe_with_version/samba:samba:4.0.0
  * http://localhost:port/v1/cpe_with_version/samba:samba:4.0.0,apache:http_server:2.4.4
  * Don't forget to encode the URI if that has special characters, example:
    * URI::encode('/v1/cpe_with_version/cisco:ios:15.4%282%29t1')

* List all the available CPEs with versions

  * http://localhost:port/v1/cpe_with_versions

## Additional Information

  * [Deploying the CVE Server with Capistrano and Ngnix](https://github.com/SpiderLabs/cve_server/wiki/Deploying-the-CVE-Server-with-Capistrano-and-Ngnix)

## Other installation method

  1. Clone our repository.

    git clone https://github.com/SpiderLabs/cve_server.git

  2. Install the ruby dependencies.

    bundle install

  3. Configure your database.

    vi config/database.yml

  4. Download, create and populate the database for your environment from the National Vulnerability Database via the NVD CVE/CPE API.
     Note: The new API service is JSON only.    
     [NVD API URL](https://services.nvd.nist.gov/rest/json/cves/1.0).

    RACK_ENV=development ./bin/nvd_download_and_seed
    ** The download may take hours to complete **
 
  5. Start the server.

    RACK_ENV=development puma

## License
  CVEServer is released under the [MIT License](https://www.opensource.org/licenses/MIT)
