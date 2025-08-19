# Ex.No: 3  Basic movements in Unity 
### DATE: 19-08-2025                                                                            
### REGISTER NUMBER : 212223040166
### AIM: 
 To learn the basic movements translation,scaling and rotation of game objects through code.
### Procedure:
1. Setup the Scene
2. Open Unity and create a 3D Scene.
3. Add three objects:Cube → Rename to Object1 (for movement),Sphere → Rename to Object2 (for rotation).Capsule → Rename to Object3 (for scaling).
4. Add the Script,Create a C# Script → Name it TransformOperations.cs.
5. Write the code for translation,scaling and rotation,save and close the script
6. Save the script
7. Select any empty GameObject (or create one: GameObject → Create Empty).
8. Attach the TransformOperations script to it.
9. In the Inspector, assign Object1 → Drag the Cube,Object2 → Drag the Sphere.Object3 → Drag the Capsule.
10. Run the Scene Press Play ▶️ in Unity
11. Stop the program.
### Program 
```
using UnityEngine;
public class TransformOperations : MonoBehaviour
{
    public Transform o1;
 public Transform o2;
 public Transform o3;
 void Start()
 {
    

 }

 // Update is called once per frame
 void Update()
 {
     o1.Translate(0.1f, 0, 0);
     o2.Rotate(0.2f, 0, 0);
     o3.localScale += new Vector3(0, 0.2f, 0);
 }
}
```
### Output:

<img width="1920" height="1080" alt="Screenshot 2025-08-19 142723" src="https://github.com/user-attachments/assets/81e38584-042a-4bf9-b1b6-4da1660dbda7" />

<img width="1920" height="1080" alt="Screenshot 2025-08-19 142906" src="https://github.com/user-attachments/assets/f536c15e-affa-4b25-a9b1-a60561fd5eac" />








### Result:
Thus the basic movement is learned through scripting


