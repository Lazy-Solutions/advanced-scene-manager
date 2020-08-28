## What is Advanced Scene Manager?
Advanced Scene Manager is a new and improved scene management system for [Unity](https://unity.com/). Get it at the [Unity Asset Store!](https://assetstore.unity.com/)

Advanced Scene Manager allows you to assign [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as chilren to a [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) (commonly referred to as collections). 
When a [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) is opened all existing scenes will be closed and the newly opened [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) will have its associated [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) opened.

Only one [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) can be open at a time, but [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) can still be opened without a parent.<br/><br/>
 
## How do I use it?
The [Scene Manager Window](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be accessed from 'File -> Scene Manager...' menu item. The [Scene Manager window](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be used to create and Remove [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and assign any [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as children.

![alt text](https://github.com/Zumwani/advanced-scene-manager/blob/master/images/File-menu-and-scene-manager-window.png "File menu and scene manager window")


​

[Collections](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) can be used like this:
```C#

using AdvancedSceneManager;

public MyScript : MonoBehaviour
{
    
    public SceneCollection collection;
    public Scene scene;
    
    public void DoStuff()
    {     
    
        //All collection functions use a loading screen, if one is defined
        collection.Open();        //Close all existing scenes and open scenes in collection
        collection.Close();       //Closes all scenes
        collection.Toggle();      //Toggles the collection on or off
        collection.Toggle(true);  //Makes sure the collection is open
        collection.Toggle(false);  //Makes sure the collection is closed
        
        //All scene functions open it as stand-alone (without collection)
        scene.Open();         //Opens the scene, stand-alone, additive
        scene.OpenSingle();   //Opens the scene, stand-alone, closes all existing scenes and collections
        scene.Close();        //Closes the scene, stand-alone
        scene.Toggle();       //Toggles the scene on or off, stand-alone
        scene.Toggle(true);   //Makes sure that the scene is open, stand-alone
        scene.Toggle(false);  //Makes sure that the scene is closed, stand-alone
        
        //All the above are proxy functions for functions in SceneManager.standalone or SceneManager.collection 
        SceneManager.standalone.Open(scene);
        SceneManager.collection.Open(collection);
        
    }
    
}
```
[Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and [Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) can also be opened from [UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html), such as from a [Button](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Button.html).
<br/><br/>
## Where can I get it!?
Advanced Scene Manager is available at the Unity Asset Store, [get it now!](https://assetstore.unity.com/)<br/><br/>
