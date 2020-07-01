# Advanced Scene Manager
​
## What is Advanced Scene Manager?
Advanced Scene Manager is a new and improved scene management system for [Unity](https://unity.com/). Get it at the [Unity Asset Store!](https://assetstore.unity.com/).

Advanced Scene Manager allows you to assign [scenes](https://github.com/Zumwani/advanced-scene-manager/wiki/Scene) as chilren to a [Root Scene](https://github.com/Zumwani/advanced-scene-manager/wiki/Root-Scene) (name pending). 
When a Root Scene is opened the current open Root Scene and any non-parented scenes will be closed and the newly opened Root Scene will have its associated scenes opened.

Only one Root Scene can be open at a time, but scenes can still be opened without a parent.

​
## How do I use it?
The Scene Manager Window can be accessed from 'File -> Scene Manager' menu item. The Scene Manager can be used to create and Remove Root Scenes and assign any scenes as children.

The Root Scenes can be used like this:
```C#
public MyScript : MonoBehaviour
{
    
    public RootScene rootScene;
    public Scene scene;
    
    public void OpenScene()
    {
        //Close existing scene and any scene-less sub scenes
        rootScene.Open();
    }
    
    public void OpenSubScene()
    {
        //Opens the sub scene without a parent, additive
        scene.Open();
    }
    
    public void CloseSubScene()
    {
        //Closes the sub scene without a parent
        scene.Close();
    }
    
}
```
Root Scenes and Scenes can also be opened from [UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html), such as from a [Button](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Button.html).

​
## Where can I get it!?
Advanced Scene Manager is available at the Unity Asset Store, [get it now!](https://assetstore.unity.com/)
​
