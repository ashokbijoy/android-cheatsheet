# Android Cheatsheet

## Activity and Fragment lifecycles
![lifecycles](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/dabe9ea1-d26b-460a-92a1-39c4ed6eece4/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20200522%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20200522T144016Z&X-Amz-Expires=86400&X-Amz-Signature=e3a76b7d9b80f87df5d2f62ed421fc8d558022c4d6117f2ebd325b4541fec16b&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

|   Callback    |              When               |                         What                        |Is Activity visible|
| --------------|---------------------------------|-----------------------------------------------------|:-----------------:|
|onCreate()     | Activity is first created       | All the necessary UI elements should be initialized | no                |
| onStart()     | Activity becomes visible to user| Code that maintains the UI, start async tasks (get data from API or database), register listeners                                                                           | yes               |
| onResume()    | Activity becomes interactable to user| Starts animations                              | yes               |
| onPause()     | User is leaving the activity     | Stops animations                                   |partially visible  |
| onStop()      | Activity is no longer visible to user| Unregisters listeners and resources allocated in onStart()|no      |
| onRestart()   | Activity in the stopped state is about to start again (on back click) | Cursor objects should be re-queried                                                                                                         | no                |
| onDestroy()   | Activity is destroyed from memory|                                                    | no                |
