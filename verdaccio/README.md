A lightweight private npm proxy registry
### Package Installation 
Install Verdaccio package
```
npm i verdaccio -g
```
Install verdaccio-offline-storage plugin.
(It lists all the locally available packages in the web ui AND rewrites on-the-fly the packages definitions so only locally available versions are recognized)
```
npm i verdaccio-offline-storage -g
```
### Configuration for verdaccio-offline-storage
Edit the config.yaml
```
# Example: C:\Users\ACCOUNTNAME\.config\verdaccio
# Add this and Verdaccio will load the plugin  
store:
  offline-storage:
# Now on, every package with no `proxy` defined will be resolved locally! 
# Optionally, if you want to resolve locally EVERY package (like in the v1 version of this plugin) 
# just add this to the config: 
offline: true
```
### To cache tarball of npm install in storage
Clean npm cache before npm install
```
npm cache clear -f
npm install <PACKAGENAME> --registry http://localhost:4873
```
### Source
- [node-verdaccio](node-verdaccio.7z)
- [config.yaml](config.yaml)