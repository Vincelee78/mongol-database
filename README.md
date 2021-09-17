![CI logo](https://codeinstitute.s3.amazonaws.com/fullstack/ci_logo_small.png)

Welcome Vincelee78,

This is the Code Institute student template for Gitpod. We have preinstalled all of the tools you need to get started. You can safely delete this README.md file, or change it for your own project. Please do read it at least once, though! It contains some important information about Gitpod and the extensions we use. The last update to this file was: **July 2, 2021**

## Gitpod Reminders

To run a frontend (HTML, CSS, Javascript only) application in Gitpod, in the terminal, type:

`python3 -m http.server`

A blue button should appear to click: _Make Public_,

Another blue button should appear to click: _Open Browser_.

To run a backend Python file, type `python3 app.py`, if your Python file is named `app.py` of course.

A blue button should appear to click: _Make Public_,

Another blue button should appear to click: _Open Browser_.

In Gitpod you have superuser security privileges by default. Therefore you do not need to use the `sudo` (superuser do) command in the bash terminal in any of the lessons.

To log into the Heroku toolbelt CLI:

1. Log in to your Heroku account and go to *Account Settings* in the menu under your avatar.
2. Scroll down to the *API Key* and click *Reveal*
3. Copy the key
4. In Gitpod, from the terminal, run `heroku_config`
5. Paste in your API key when asked

You can now use the `heroku` CLI program - try running `heroku apps` to confirm it works. This API key is unique and private to you so do not share it. If you accidentally make it public then you can create a new one with _Regenerate API Key_.

------
mongo "mongodb+srv://cluster0.ii2xi.mongodb.net/" --username root
## Release History

We continually tweak and adjust this template to help give you the best experience. Here is the version history:

**July 2 2021:** Remove extensions that are not available in Open VSX.

**June 30 2021:** Combined the P4 and P5 templates into one file, added the uptime script. See the FAQ at the end of this file.

**June 10 2021:** Added: `font_fix` script and alias to fix the Terminal font issue

**May 10 2021:** Added `heroku_config` script to allow Heroku API key to be stored as an environment variable.

**April 7 2021:** Upgraded the template for VS Code instead of Theia.

**October 21 2020:** Versions of the HTMLHint, Prettier, Bootstrap4 CDN and Auto Close extensions updated. The Python extension needs to stay the same version for now.

**October 08 2020:** Additional large Gitpod files (`core.mongo*` and `core.python*`) are now hidden in the Explorer, and have been added to the `.gitignore` by default.

**September 22 2020:** Gitpod occasionally creates large `core.Microsoft` files. These are now hidden in the Explorer. A `.gitignore` file has been created to make sure these files will not be committed, along with other common files.

**April 16 2020:** The template now automatically installs MySQL instead of relying on the Gitpod MySQL image. The message about a Python linter not being installed has been dealt with, and the set-up files are now hidden in the Gitpod file explorer.

**April 13 2020:** Added the _Prettier_ code beautifier extension instead of the code formatter built-in to Gitpod.

**February 2020:** The initialisation files now _do not_ auto-delete. They will remain in your project. You can safely ignore them. They just make sure that your workspace is configured correctly each time you open it. It will also prevent the Gitpod configuration popup from appearing.

**December 2019:** Added Eventyret's Bootstrap 4 extension. Type `!bscdn` in a HTML file to add the Bootstrap boilerplate. Check out the <a href="https://github.com/Eventyret/vscode-bcdn" target="_blank">README.md file at the official repo</a> for more options.

------

## FAQ about the uptime script

**Why have you added this script?**

It will help us to calculate how many running workspaces there are at any one time, which greatly helps us with cost and capacity planning. It will help us decide on the future direction of our cloud-based IDE strategy.

**How will this affect me?**

For everyday usage of Gitpod, it doesn’t have any effect at all. The script only captures the following data:

- An ID that is randomly generated each time the workspace is started.
- The current date and time
- The workspace status of “started” or “running”, which is sent every 5 minutes.

It is not possible for us or anyone else to trace the random ID back to an individual, and no personal data is being captured. It will not slow down the workspace or affect your work.

**So….?**

We want to tell you this so that we are being completely transparent about the data we collect and what we do with it.

**Can I opt out?**

Yes, you can. Since no personally identifiable information is being captured, we'd appreciate it if you let the script run; however if you are unhappy with the idea, simply run the following commands from the terminal window after creating the workspace, and this will remove the uptime script:

```
pkill uptime.sh
rm .vscode/uptime.sh
```
mongo "mongodb+srv://cluster0.ii2xi.mongodb.net/" --username root
**Anything more?**

Yes! We'd strongly encourage you to look at the source code of the `uptime.sh` file so that you know what it's doing. As future software developers, it will be great practice to see how these shell scripts work.

---

<!-- #Mongo commands -->

<!-- show all databases -->
show databases

<!-- set active bases -->
use sample_airbnb

<!-- to show all collections -->
show collections

<!-- clear the screen -->
cls


<!-- show current database -->
db

<!-- to find all documents of a collection -->
db<name of collection>.find()

<!-- next 10 documents -->
it

<!-- to beautify  -->
db<name of collection>.find().pretty

<!-- projection -->
display only certain keys from documents

db.listingsAndReviews.find({},{
    'name':1,
    'address.country':1
}).pretty()

<!-- limit 5 -->
db.listingsAndReviews.find({},{
    'name':1,
    'address.country':1
}).pretty().limit(5)

<!-- filtering -->
<!-- find all listings with exactly 3 beds -->
<!-- first criteria is 3 beds -->
db.listingsAndReviews.find({
    'beds':3 
},{
    'name':1,
    'beds':1
}).pretty()

db.listingsAndReviews.find({
    'beds':2,
    'bedrooms':2
},{
    'name':1,
    'address.country':1,
    'bedrooms':1
}).pretty()

<!-- search by a query key -->

db.listingsAndReviews.find({
    'beds':2,
    'bedrooms':2,
    'address.country':'Brazil'
},{
    'name':1,
    'address.country':1,
    'bedrooms':1
}).pretty()

<!-- $lt, $lte, $ne -->
db.listingsAndReviews.find({
    'beds': {
        $gte:3
    }
},{
    'name':1,
    'address.country':1,
    'beds':1
}).pretty()

<!--  any of them $in in amenities ARRAY it will shortlist-->

db.listingsAndReviews.find({
    'amenities': {
        $in:['Oven,'Microwave']
    }
},{
    'name':1,
    'address.country':1,
    'beds':1,
    'amenities':1
}).pretty()

<!-- all of the items $all in amenities ARRAY -->

db.listingsAndReviews.find({
    'amenities': {
        $all:['Oven,'Microwave']
    }
},{
    'name':1,
    'address.country':1,
    'beds':1,
    'amenities':1
}).pretty()

<!-- Select by objectID uses the sample_mflix database-->
db.movies.find({
    '_id':ObjectId('123123')
}).pretty()

<!-- regular expression -->
<!-- find all the listings that has the word 'spacious' and $options is to ignore CAPS -->
db.listingsAndReviews.find({
    'name': {
        '$regex':'spaciouS',
        '$options':'i'
    }
},{
    'name':1,
    
}).pretty()

<!-- 2a -->
db.companies.find({
    'founded_year':2006
},{
    'name':1,
    'founded_year':1
    
}).pretty()

<!-- 2b -->
db.companies.find({
    'founded_year':{
        $gt:2000
    }
},{
    'name':1,
    'founded_year':1
    
}).pretty()

<!-- 2c -->

db.companies.find({
    'founded_year':{
        $gte:1900,
        $lte:2010
    }
},{
    'name':1,
    'founded_year':1
    
}).pretty()

<!-- 3a -->

db.companies.find({
    'acquisition.price_amount':{
        $gt:100000000
        
    }
},{
    'name':1,
    'acquisition.price_amount':1,
    'acquisition.price_currency_code':1

    
}).pretty()

<!-- 3b -->

db.companies.find({
    'acquisition.price_amount':{
        $gt:10000000   
    },
    'acquisition.price_currency_code': 'USD'
},{
    'name':1,
    'acquisition.price_amount':1,
    'acquisition.price_currency_code':1

    
}).pretty()

<!-- slide 2.2 -->

db.inspections.find({
    'result': "Violation Issued"
    
},{
    'business_name':1,
    'result':1

}).pretty()

<!-- 2.3 -->
db.inspections.find({
    'address.city':"NEW YORK",
    'result': "Violation Issued"
    
},{
    'business_name':1,
    'result':1,
    'address.city':1

}).pretty()

<!-- 2.4 -->

db.inspections.count({
    'address.city':"NEW YORK",
    

})


db.inspections.find({
    'address.city':"NEW YORK",
    

}).count()

<!-- 2.5 $ne --> 

db.inspections.find({
    'address.city': {
        '$regex':'ridgewood',
        '$options':'i'
    },
    'result': {
        '$ne':"Violation Issued"
    }
}).count()

<!-- 3.1 -->

db.accounts.find({
    'products': {
        '$in':["InvestmentStock"]
    }
    },
    {
        'account_id':1,
        'products':1

    
}).pretty()

<!-- 3.2 -->
db.accounts.find({
    'products': {
        '$all':["InvestmentStock","Commodity"]
    }
    },
    {
        'account_id':1,
        'products':1

    
}).pretty()

<!-- 3.3 -->

db.accounts.find({
    'products': {
        '$in':["CurrencyService","Commodity"]
    }
    },
    {
        'account_id':1,
        'products':1

    
}).pretty()

<!-- 3.4 $nin(not included in array)-->

db.accounts.find({
    'products': {
        '$nin':["CurrencyService"]
    }
    },
    {
        'account_id':1,
        'products':1

    
}).pretty()

<!-- 3.5 -->

db.accounts.find({
    'limit':{
        $gt:1000
    },
    'products': {
        '$all':["InvestmentStock","InvestmentFund"]
    }
    },
    {
        'account_id':1,
        'products':1

    
})

db.animals.insert({
    'name': 'Fluffy',
    'age': 3,
    'breed':'golden'

})

db.students.insertMany([
    {
    'Name': 'Jane Doe',
    'Age': 13,
    'Subjects': ['Defense Against the Dark Arts', 'Charms', 'History of Magic'],
    'Data Enrolled': ISODate('2016-05-13')
},
{
    'Name': 'James Verses',
    'Age': 14,
    'Subjects': ['Transfiguration', 'Alchemy'],
    'Data Enrolled': ISODate('2015-06-15')
},
{
    'Name': 'Jonathan Goh',
    'Age': 12,
    'Subjects': ['Divination', 'Study of Ancient Runes'],
    'Data Enrolled': ISODate('2017-04-16')

}

])

db.students.find({

    'Subjects':'Divination',
},
{
    'Subjects':1,

}).pretty()

<!--  

$set as the 2nd argument {
    '$set':{
    'age':1.5
    }
    }) -->

    db.students.update({
        "_id" : ObjectId("61444414a9aa7ede8d49acb7")
    },
    {
        '$set':{
            'status': 'living'
        }
    
    })

db.students.remove({
    "_id" : ObjectId("61444414a9aa7ede8d49acb7")
})

db.students.update({
        
    },
    {
        '$set':{
            'Age': +1
        }
    
    })

    db.students.update({
        "_id" : ObjectId("61444414a9aa7ede8d49acb7")
    },
    {
        '$set':{
            'Data Enrolled': {
                ISODate:('2018-05-13')

                
            }
        }
    
    })

    db.students.updateMany({
    },
    {
        '$inc':{
            'Age':1
        }
    })

    db.students.update({
        "_id" : ObjectId("61444414a9aa7ede8d49acb6")
    },
    {
        '$set':{
            'Age': 13
                
            }
        
    
    })

    db.students.find()

    db.students.update({
        "_id" : ObjectId("61444414a9aa7ede8d49acb5")
    },
    {
        '$set':{
            'Name': "Jane Doe Jr",
            'Age':11
    
            }
        
    })

    db.animals.insert({
    'name':'Cookie',
    'age': 3,
    'breed':'Lab Retriever',
    'type':'Dog',
    'checkups':[]
})

db.animals.insertMany([{
    
    Name: 'Dash',
    Age: 3,
    Breed: 'Hamster',
    Species: 'Hamster',
     },
    {
    Name: 'Carrot',
    Age: 1.5,
    Breed: 'Australian Dwarf',
    Species: 'Rabbit'

    
}])

db.animals.update({
    Name:'Carrot'
},
{
    "Name" : "carrot", 
    "age" : 1.5, 
    "Breed" : "Australian Dwarf",
    "Species" : "Rabbit"
    

})

db.<collection.name>.drop()

db.animals.update({
    Name:'Dash'
},
{
    "Name" : "Dash", 
    "age" : 4.5, 
    "Breed" : "Winter White",
    "Species" : "Hamster"
    

})

db.animals.remove({
    Name:'Jorden'
})

db.accounts.update({
    _id: ObjectId('5ca4bbc7a2dd94ee5816238d')
},{
    '$set':{
        'products.0':'Stock',
        'products.4':'stocks'
        
    
    }

})

db.accounts.update({
    _id:ObjectId('61445c757c693bd2f43fb7e2')
}, {
    '$push': {
        'checkups': {
            '_id':ObjectId(),
            'name':'Dr Tan',
            'diagnosis':'Diabetes',
            'treatment':'Medication'
        }
    }
})

db.animals.find().pretty()

db.animals.update({
    _id:ObjectId('614467aa11a208cae4fea1a7')
},{
    '$push':{
        'checkups': {
            '_id':ObjectId(),
            'name':'Dr Zhao',
            'diagnosis':'Diabetes',
            'treatment':'Medication'
        }
    }
})


})


db.animals.update({
    '_id': ObjectId('614467aa11a208cae4fea1a9')
},{
    '$set':{
        'checkups.0.name':'Dr Su'
    }

})

db.animals.updateMany({
    'checkups': {
        '$elemMatch':{
            '$all':{
                'name':['Dr Zhao']
       
         }
         }
    }
},{
    '$set':{
        'checkups.$.name':'Dr Tan'
    }

})

db.animals.update({
    'checkups.id': ObjectId("614467aa11a208cae4fea1a8")
}, {
    '$set': {
        'checkups.$.name':'Dr cdf',
        'checkups.$.date': ISODate('2000-06-18')
    }
})

mongo "mongodb+srv://cluster0.ii2xi.mongodb.net/" --username root
