# Busybox
Android busybox library

Usage:

```
repositories {
	...
	maven { url 'https://jitpack.io' }
}
dependencies {
	...
	compile 'com.github.yzheka:Busybox:+'
}
```
Application onCreate method:

```
	@Override
	public void onCreate() {
		super.onCreate();
		try{
			Busybox.init(this);
		}catch(IOException e){
			//This should not happen but something went wrong while extracting busybox binary
		}
	}
```
In Code:
```
	try{
		String[] lines=Busybox.execute("whoami");
	}catch(IOException e){
		//Error executing command
	}
```
