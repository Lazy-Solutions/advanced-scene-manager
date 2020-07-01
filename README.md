## What is Advanced Scene Manager?
Advanced Scene Manager is a new and improved scene management system for [Unity](https://unity.com/). Get it at the [Unity Asset Store!](https://assetstore.unity.com/)

Advanced Scene Manager allows you to assign [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as chilren to a [Root Scene](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) (name pending). 
When a [root scene](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) is opened the currently open [root scene](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) and any non-parented [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) will be closed and the newly opened [root scene](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) will have its associated [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) opened.

Only one Root Scene can be open at a time, but scenes can still be opened without a parent.<br/><br/>
 
## How do I use it?
The [Scene Manager Window](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be accessed from 'File -> Scene Manager' menu item. The [Scene Manager](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene-Manager-Window) can be used to create and Remove [Root Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) and assign any [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as children.

The [Root Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) can be used like this:
```C#
public MyScript : MonoBehaviour
{
    
    public RootScene rootScene;
    public Scene scene;
    
    //TODO: Uhh.. Let's not do this in Update(), that's weird :)
    public void Update()
    {        
        rootScene.Open(); //Close existing scene and any scene-less sub scenes
        scene.Open();     //Opens the sub scene without a parent, additive
        scene.Close();    //Closes the sub scene without a parent
    }
    
}
```
[Root Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) and [Scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) can also be opened from [UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html), such as from a [Button](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Button.html).
<br/><br/>
## Where can I get it!?
Advanced Scene Manager is available at the Unity Asset Store, [get it now!](https://assetstore.unity.com/)<br/><br/>
