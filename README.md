vagrant
=======

### Pre-requirements:
Git

### 1. Install VirtualBox
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

### 2. Install Vagrant
- [Vagrant] (http://www.vagrantup.com/)

### 3. Executing the vagrant command to build up env
<pre>
  $ vagrant up
</pre>

More info to work with Vagrant, visit [documents](http://docs.vagrantup.com/v2/cli/index.html)

### 4. Open SSH connection
<pre>
  $ vagrant ssh
</pre>

### 5. Setting evn for yeoman in vagrant
 * What's in the box:
    - curl
    - RVM with Ruby 2.0.0 or later
    - NodeJs and NPM (included: Bower, Grunt)
    - Compass
    - PhantomJS
    - JPEGTRAN
    - Yeoman

### 6. Install Heroku
  - [Heroku] (https://devcenter.heroku.com/articles/quickstart)

  - heroku-toolbelt

### 7. Heroku
<pre>
  $ npm install -g generator-heroku
<pre>

<pre>
  $ yo heroku
</pre>

### 8. Config Grunfile.js for heroku
<pre>
  copy: {
    dist: {
      file: [{
        expand: true,
        dest: '<%= yeoman.dist %>',
        cwd: 'heroku',
        src: '*',
        rename: function (dest, src) {
          var path = require('path');
          if (src === 'distpackage.json') {
          return path.join(dest, 'package.json');
        }
        return path.join(dest, src);
      }]
    }
  }
</pre>

### 9. Create app on Heroku
<pre>
  $ cd dist/
  $ heroku apps:create
</pre>

#Heroku Rename app:
<pre>
  $ heroku rename name_app
</pre>

### 10. Deployment app on Heroku
<pre>
$ grunt build
</pre>

#Push all files in dist folder on heroku:
<pre>
  $ git push heroku master
</pre>

### Notes
* Working folders: /home/vagrant/app

### Get the site up and running
* Start the server
<pre>
  $ grunt serve
</pre>

* Shutdown server
<pre>
  $ grunt halt
</pre>

## Known Issues:
If you encounter a problem concerning npm when you run "angular yo". Workarounds as follows:

- Install Node.js with NVM (Node Version Manager)

<pre>
  $ curl https://raw.githubusercontent.com/creationix/nvm/v0.10.0/install.sh | sh
  $ nvm install 0.10
  $ nvm use 0.10
  $ nvm alias default 0.10
</pre>
