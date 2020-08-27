## What is Advanced Scene Manager?
Advanced Scene Manager is a new and improved scene management system for [Unity](https://unity.com/). Get it at the [Unity Asset Store!](https://assetstore.unity.com/)

Advanced Scene Manager allows you to assign [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as chilren to a [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) (commonly referred to as collections). 
When a [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) is opened the currently open [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and all stand-alone [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) will be closed and the newly opened [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) will have its associated [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) opened.

Only one [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) can be open at a time, but [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) can still be opened without a parent.<br/><br/>
 
## How do I use it?
The [Scene Manager Window](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be accessed from 'File -> Scene Manager...' menu item. The [Scene Manager](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be used to create and Remove [Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and assign any [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as children.

![alt text](https://github.com/Zumwani/advanced-scene-manager/blob/master/images/File-menu-and-scene-manager-window.png "File menu and scene manager window")

[Collections](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) can be used like this:
```C#
public MyScript : MonoBehaviour
{
    
    public SceneCollection collection;
    public Scene scene;
    
    //TODO: Uhh.. Let's not do this in Update(), that's weird :)
    public void Update()
    {        
        collection.Open();   //Close all existing scenes and open scenes in collection, also shows loading screen
        scene.Open();        //Opens the scene, stand-alone, additive
        scene.OpenSingle();  //Opens the scene, stand-alone, closes all existing scenes and collections
        scene.Close();       //Closes the scene, stand-alone
        scene.Toggle();      //Toggles the scene on or off, stand-alone
        scene.Toggle(true);  //Makes sure that the scene is open, stand-alone
    }
    
}
```
[Scene Collection](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Collection) and [Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) can also be opened from [UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html), such as from a [Button](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Button.html).
<br/><br/>
## Where can I get it!?
Advanced Scene Manager is available at the Unity Asset Store, [get it now!](https://assetstore.unity.com/)<br/><br/>
