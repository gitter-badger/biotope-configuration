# configurationLoader

configurationLoader.js loads configurations from a json file and then merges them with existing confiugrations using a flag (overwriteInlineConfigs) to decide which parameters should be overwritten. By default this flag is false, that is inline configurations take precedence over those set in json file. The loader returns a promise object which once resolved will give access to configuration object. This object has also getter and setter methods which should be used to get and set configuration parameters.

**Usage**
```javascript
configurationLoader({
	json: 'url.to.configuration.json',
	data: inline.configuration,
	overwriteInlineConfigs: [optional boolean parameter]
}).then(function(data) {
	window.myProject.configuration = data;
	// It's now safe to run scripts depending on configuration parameters
});

var test = myProject.configuration.get('nameOfProperty');
```