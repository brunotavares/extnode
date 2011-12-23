ExtNode
======

[Ext JS](http://http://www.sencha.com/products/extjs/) Foundation exported to NodeJS. It only includes
the JavaScript utilities that really matter for NodeJS development. [Check the docs](http://brunotavares.github.com/extnode) 
for a full list of what is included.

Current version: Ext JS 4.1 beta

Getting it
----------

Standard node module install should do:

	$ npm install extnode
	
Usage
-----

	var Ext = require('extnode');
	
You can also use the developer version, which is uncompressed and debuggable.

	var Ext = require('extnode/dev');
	
Example
-------

	var Ext = require('extnode');
	
	//you can define classes
	Ext.define('App.model.Person', {
	  config: {
	    name: '',
	    age: 0
	  },
	  constructor: function(config) {
	    this.initConfig(config);
	    return this;
	  }
	});
	
	//create instances
	var John = new App.model.Person({
	  name: 'John',
	  age: 27
	});

	
	//have getters and setters automatically
	console.log(John.getName()); //John
	console.log(John.getAge()); //27
	John.setAge(28);
	console.log(John.getAge()); //28

	//and extend
	Ext.define('App.model.Developer',{
	  extend: 'App.model.Person',
	  drinkCoffee: function(){
	    console.log('drinking cooffee...');
	  }
	});

	var Bruno = new App.model.Developer({
	  name: 'Bruno',
	  age: 22
	});

	console.log(Bruno.getName()); //Bruno
	Bruno.drinkCoffee(); //drinking coffee...
	
Licensing
---------

Copyright (c) 2011 Sencha Inc

Contact:  http://www.sencha.com/contact

Commercial Usage
Licensees holding valid commercial licenses may use this file in accordance with the Commercial Software License Agreement provided with the Software or, alternatively, in accordance with the terms contained in a written agreement between you and Sencha.

If you are unsure which license is appropriate for your use, please contact the sales department at http://www.sencha.com/contact.

For more check [license.txt](https://github.com/brunotavares/extnode/blob/master/license.txt)