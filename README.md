# Advanced Scene Manager

## What is Advanced Scene Manager?
Advanced Scene Manager is a new and improved scene management system for [Unity](https://unity.com/). Get it at the [Unity Asset Store](https://assetstore.unity.com/)!.

Advanced Scene Manager allows you to assign Sub Scenes (regular unity scenes, name pending) as chilren to a Scene (name pending). 
When a Scene is opened the current open Scene and any Scene-less Sub Scenes will be closed and the newly opened Scene will have its associated Sub Scenes open. 

Only one Scene can be open at a time, but Sub Scenes can be opened manually without a parent.

## How do I use it?
The Scene Manager Window can be accessed from 'File -> Scene Manager' menu item. The Scene Manager can be used to create and Remove Scenes and assign any Sub Scene children.

The Scenes can then be used like this:
```
public MyScript : MonoBehaviour
{
    
    public Scene scene;
    public SubScene subScene;
    
    public void OpenScene()
    {
        //Close existing scene and any scene-less sub scenes
        scene.Open();
    }
    
    public void OpenSubScene()
    {
        //Opens the sub scene without a parent, additive
        subScene.Open();
    }
    
    public void CloseSubScene()
    {
        //Closes the sub scene without a parent
        subScene.Close();
    }
    
}
```
Scenes can also be opened from [UnityEvents](https://docs.unity3d.com/Manual/UnityEvents.html), such as from a [Button](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/script-Button.html).
