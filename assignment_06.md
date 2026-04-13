# Lab 6: Rigid body physics

This instruction will be slightly different from the previous ones I've posted. This one focuses mostly on the tasks you'll need to accomplish, and less on the "how-to" part. As for the how to part, I'll link some of the tutorials I've found useful when trying to figure it myself when learning Unity. 

## Resources

- [A micro-lecture on rigid body and colliders](https://www.youtube.com/watch?v=K4JwfpXJFik)
- [AddForce method - interacting with rigid bodies](https://www.youtube.com/watch?v=SveLLDfeGcQ)
- [AddTorque method - spinning objects](https://www.youtube.com/watch?v=qGz0nQoCwNs)
- [Detect collisions - Unity documentation](https://docs.unity3d.com/6000.3/Documentation/ScriptReference/Collision-gameObject.html)

## Tasks


### Task 1

Watch the first tutorial and create a few physical objects in a scene. Use different shapes and masses. Create a floor and walls to contain the objects. Add constant forces to all of the objects to make them move. Observe collisions and friction between objects and the floor/walls. Add screenshots and a short description of what you observed to your report. Play around with parameters of rigid bodies and forces and see how they affect the behavior of the objects. **(15%)**

### Task 2

Watch the second tutorial and use it to build a scene consisting of source of wind and a plane. Use the code to spawn or drop a few objects of different shapes and masses. Make the wind blow and observe the behavior of the objects. Add screenshots and a short description of what you observed to your report. **(20%)**

### Task 3

Watch the third tutorial and use the knowledge from all of the tutorials to create a game of bowling. Spawn 10 pins in a triangle formation at the end of the lane (you can use cylinders or some assets that you find). Make the ball as physically accurate as possible (i. e. if dropped from a height, it should bounce a bit). Allow the player to adjust height and and horizontal position of the ball before the throw. Apply the force to the ball in the point the player clicks the ball with the mouse. Add screen recording of the game to your report. Test if you need to add torque separately of adding force to the ball. **(40%)**

**Hint:** You can detect the click on the ball using raycasting:

```csharp
Ray ray = Camera.main.ScreenPointToRay(Input.mousePosition);
RaycastHit hit;

if (Physics.Raycast(ray, out hit))
{
    if (hit.rigidbody != null)
    {
        // Apply physics here
    }
}
```

### Task 4
Watch [this video (if you haven't seen it yet)](https://www.youtube.com/watch?v=HEfHFsfGXjs) and try to recreate the simulation in Unity. Build a scene with a minimal UI that will display the result. Expose the mass ratio to the editor. Does the result achieved in Unity match the one from the video? Why or why not? Add screenshots and values of masses and counted bounces to your report. **(25%)**
