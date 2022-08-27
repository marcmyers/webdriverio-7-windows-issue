# Webdriver.io 7 Windows Issue
There appears to be an issue with Webdriver.io 7 where the selenium-standalone-server is not being terminated when tests are done executing

## Steps To Reproduce
Install project dependencies:
> npm install

Execute the tests using:
> npm test

After the tests are complete, execute the tests again.
You should see the following error:
> ERROR @wdio/selenium-standalone-service: Error: Port 4444 is already in use.

To verify that the selenium-standalone-server is sitll running, open a browser and goto:
> http://localhost:4444/ui/index.html#/

To re-execute the tests, you'll need todo the following:
> netstat -ano | findstr :4444

> taskkill /PID 00000 /F

Replace 00000 with the PID from the process running on 4444
