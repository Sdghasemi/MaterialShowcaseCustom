# MaterialShowcaseCustom
A Material Design themed ShowcaseView for Android

This library is heavily inspired by the original [MaterialShowcaseView library][1].

Since Google introduced the Material design philosophy I have seen quite a few apps with a nice clean, flat showcase view (the Youtube app is a good example). The only library out there however is the [original one][1]. This was a great library for a long time but the theming is now looking a bit dated.

![Logo](http://i.imgur.com/QIMYRJh.png)


![Animation][2]

# Gradle
--------

[![jitpack][4]][5]

Add the jitpack repo to your your project's build.gradle at the end of repositories [Why?](#why-jitpack)

/build.gradle
```groovy
allprojects {
	repositories {
		jcenter()
		maven { url "https://jitpack.io" }
	}
}
```

Then add the dependency to your module's build.gradle:

/app/build.gradle
```groovy
compile 'com.github.Sdghasemi:MaterialShowcaseCustom:1.1.0'
```

NOTE: Some people have mentioned that they needed to add the @aar suffix to get it to resolve from JitPack:
```groovy
compile 'com.github.Sdghasemi:MaterialShowcaseCustom:1.1.0@aar'
```

# How to use
--------
This is the basic usage of a single showcase view, you should check out the sample app for more adbvanced usage.

```java

	// single example
	new MaterialShowcaseView.Builder(this)
                .setTarget(mButtonShow)
                .setDismissText("GOT IT")
                .setContentText("This is some amazing feature you should know about")
                .setDelay(withDelay) // optional but starting animations immediately in onCreate can make them choppy
                .setSwitchLanguageText("Switch Language", new View.OnClickListener() {
                                            @Override
                                            public void onClick(View view) {
                                                // Your onClick code here...
                                            }
                                        })
                .singleUse(SHOWCASE_ID) // provide a unique ID used to ensure it is only shown once
                .show();
                
                
                
                
    	// sequence example            
    	ShowcaseConfig config = new ShowcaseConfig();
        config.setDelay(500); // half second between each showcase view

        MaterialShowcaseSequence sequence = new MaterialShowcaseSequence(this, SHOWCASE_ID);

        sequence.setConfig(config);

        sequence.addSequenceItem(mButtonOne,
                "This is button one", "GOT IT");

        sequence.addSequenceItem(mButtonTwo,
                "This is button two", "GOT IT");

        sequence.addSequenceItem(mButtonThree,
                "This is button three", "GOT IT");

        sequence.start();
                
```

# Why Jitpack
------------
Publishing libraries to Maven is a chore that takes time and effort. Jitpack.io allows me to release without ever leaving GitHub so I can release easily and more often.


# License
-------

    Copyright 2015 Dean Wild

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.





[1]: https://github.com/deano2390/MaterialShowcaseView
[2]: http://i.imgur.com/rFHENgz.gif
[3]: https://code.google.com/p/android-flowtextview/
[4]: https://img.shields.io/github/release/deano2390/MaterialShowcaseView.svg?label=JitPack
[5]: https://jitpack.io/#deano2390/MaterialShowcaseView
