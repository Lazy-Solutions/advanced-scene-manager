## What is a scene?

An ASM scene is our representation of a [SceneAsset ]()/ Unity scene. All [SceneAsset]()[s] in the project will have a corresponding Scene [ScriptableObject ]() generated for it. Aside from the slight confusion that might arise at first, this approach has numerous advantages:

* Drag and drop references in inspector:
  
  ![alt text](C:\Users\Zumwani\Documents\GitHub\advanced-scene-manager\images\Scene-reference.png "Unity event")
  
  

* [UnityEvent ]()support (t might be easier to use [SceneHelper]() as target though, since that will help filter the [object picker]() to only display scenes):
  
  ![alt text](C:\Users\Zumwani\Documents\GitHub\advanced-scene-manager\images\Unity-event.png "Unity event")
  
  

* More robust:
  
  Consider this:
  
  ```csharp
  using UnityEngine.SceneManagement;
  using AdvancedSceneManager.Models;
  
  //------Unity, Out-of-the-box------
  
  //Path: Loses reference when scene is moved, renamed, deleted...
  //Name: Loses reference when scene renamed, deleted...
  public string scene;
  //Loses reference when build index changes...
  public int sceneIndex;
  
  public void OpenSceneUnity()
  {
      SceneManager.LoadScene(scene);
      SceneManager.LoadScene(sceneIndex);
  }
  
  //------Advanced Scene Manager------
  
  //Is automatically updated when its associated SceneAsset is moved,
  //renamed and deleted.
  //Does not rely on build index.
  public Scene scene;
  
  public void OpenSceneASM()
  {
      scene.Open();
  }
  ```



## Properties

- includeInBuild
  
  Gets or sets whatever this scene should be included in build.
  
  

- isIncluded (read-only):
  
  Returns whatever the scene is currently included in build. This also takes into account whatever a scene is forced to be included, which would be any scenes that have been added to a [collection](), or is set as [splash screen]().
  
  

- path:
  
  The path to the Unity scene in the project.
  
  

- assetID:
  
  The [AssetDatabase ]()id of the SceneAsset.
  
  

- layer:
  
  The [SceneLayer ]()of this scene.
  
  

- isActive (read-only, use [Activate()]() to set it as active):
  
  Returns whatever this scene is currently the active scene.
  
  

## Methods

> The following methods can take a sceneIndex parameter which can be used to distinguish scenes that have been opened multiple times, the index is only used for the list of this scene, not all currently open scenes (i.e. if first instance of the scene is at the top of the hierarchy and the second is at the bottom, use sceneIndex: 1 for the second instance).



* T FindObject<T>(int sceneIndex = 0)
  
  Finds the component of type T in the scene object hierarchy.
  
  

* IEnumerable<T> FindObjects<T>(sceneIndex = 0)
  
  Same as above, but plural.
  
  

* GameObject[] GetRootGameObjects(int sceneIndex = 0)

        Gets the root game objects of this scene.



### Extension methods

> Most methods that are listed as extension methods are actually done through partial class methods, defined in [SceneHelper](), this is because [SceneHelper ]()makes use of [ISceneProxy ]()interface to ensure that all methods that needs to be implemented actually are.



* Open
  
  Opens the scene as [standalone]().
  
  

* OpenSingle
  
  Closes all existing scenes and collection, and opens this scene as [standalone]().
  
  

* Close
  
  Closes the first instance of this scene that is open
  
  

* Toggle
  
  Toggles the scene on or off, depending on whatever it is open or not.
  
  

* Toggle(bool enabled);
  
  Toggles the scene on or off, depending on enabled.
  
  

* [SceneAsyncOperation]()<[PreloadedSceneHelper]()> Preload
  
  Preloads the scene, which loads it into memory but does not display it.
  
  

* Activate
  
  Sets the scene as the active scene in the hierarchy.
  
  

* [IsOpenReturnValue]() IsOpen
  
  Returns whatever this scene is open.
  
  

* ([SceneCollection ]()collection, bool asLoadingScreen)[] FindCollections();
  
  Finds the [collections]() that this scene is associated with.
  
  

* OpenWithFade(float duration = 0.5f)
  
  [Open()](), but with a fade in and fade out.
  
  

* OpenSingleWithFade(float duration = 0.5f)
  
  [OpenSingle()](), but with a fade in and fade out.
  
  

* CloseWithFade(float duration = 0.5f)
  
  [Close()](), but with a fade in and fade out.
  
  

* ToggleWithFade(float duration = 0.5f)
  
  [Toggle()](), but with a fade in and fade out.
  
  

* ToggleWithFade(bool enabled, float duration = 0.5f)
  
  [Toggle(bool enabled)](), but with a fade in and fade out.


