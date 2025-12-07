---
sidebar_position: 5
---

# Chapter 5: Running Robotics Simulations in Unity

Having set up your Unity environment and imported a robot model, this chapter will guide you through running basic robotics simulations within Unity and introduce how to connect them with ROS 2. Unity's powerful rendering and physics capabilities make it an excellent platform for visually rich and realistic simulations.

## 1. Building a Simple Simulation Scene

1.  **New Scene**: In your Unity project, go to `File > New Scene`. Save it as `RobotSimulationScene`.
2.  **Add Ground Plane**: Right-click in the Hierarchy window, `3D Object > Plane`. This will serve as the ground for your robot. Position it at (0,0,0) with a scale of (1,1,1).
3.  **Add Robot Model**: Drag your imported URDF robot model (from the Assets folder) into the Hierarchy window. Position it slightly above the ground plane (e.g., Y=0.5) to let gravity take effect.
4.  **Add Lights**: Ensure your scene has adequate lighting (e.g., a `Directional Light`).
5.  **Add Obstacles (Optional)**: You can add simple 3D objects (cubes, spheres) to create obstacles for your robot. Make sure they have `Rigidbody` and `Collider` components if you want physics interactions.

## 2. Running the Simulation

Press the **Play** button at the top of the Unity Editor. Your robot should fall onto the ground plane (due to gravity) and remain stationary if no forces are applied. If it falls through the floor or flies away, check its `Rigidbody` and `Collider` components.

## 3. Basic Robot Control Script

Let's create a simple C# script to make our robot move.

1.  **Create C# Script**: In the Project window, right-click `Assets > Create > C# Script`. Name it `RobotController`.
2.  **Attach Script**: Drag the `RobotController` script onto the root GameObject of your robot model in the Hierarchy.
3.  **Edit Script**: Double-click the script to open it in your IDE (e.g., Visual Studio Code).

```csharp
using UnityEngine;

public class RobotController : MonoBehaviour
{
    public float linearSpeed = 0.5f; // Meters per second
    public float angularSpeed = 30.0f; // Degrees per second
    private Rigidbody rb;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
        if (rb == null)
        {
            Debug.LogError("Rigidbody not found on the robot! Make sure your robot has one.");
        }
    }

    void FixedUpdate() // Use FixedUpdate for physics operations
    {
        // Example: Make the robot move forward
        if (rb != null)
        {
            // Apply linear velocity
            rb.velocity = transform.forward * linearSpeed;

            // Apply angular velocity (e.g., rotate it)
            // You might want to control specific joints for realistic robot movement
            // For a simple base, we can directly rotate the whole body.
            // This is a simplified approach, real robots use joint control.
            transform.Rotate(0, angularSpeed * Time.fixedDeltaTime, 0);
        }
    }
}
```

This script is a very basic example. For a real robot, you would typically control individual joints via an inverse kinematics solver or directly apply forces.

## 4. Unity Robotics Hub and ROS 2 Integration

The **Unity Robotics Hub** is a collection of Unity packages and tools designed to streamline the development of robotics applications. It includes packages for:

-   **ROS-TCP-Connector**: Enables communication between Unity and ROS 2 over TCP.
-   **ROS-Unity-Message-Visualizer**: Visualizes ROS 2 messages directly in Unity.
-   **URDF Importer**: (Which we used previously)

To integrate with ROS 2:

1.  **Install ROS-TCP-Connector**: Follow the same steps as importing the URDF Importer (using Package Manager, Add package from Git URL) for `https://github.com/Unity-Technologies/ROS-TCP-Connector.git`.
2.  **Run ROS 2 TCP Endpoint**: In your ROS 2 environment, run the TCP endpoint:

    ```bash
    ros2 run ros_tcp_endpoint default_server_endpoint
    ```

3.  **Create ROS 2 Publishers/Subscribers in Unity**: Using the `ROSConnection` component provided by `ROS-TCP-Connector`, you can create C# scripts that publish or subscribe to ROS 2 topics.

    For example, a simple publisher in Unity might look like:

    ```csharp
    using RosMessageTypes.Std; // For StringMsg
    using Unity.Robotics.ROSTCPConnector;
    using UnityEngine;

    public class RosPublisher : MonoBehaviour
    {
        public ROSConnection ros;
        public float publishMessageFrequency = 0.5f; // seconds
        private float timeElapsed;
        private string topicName = "unity_chatter";

        void Start()
        {
            ros = ROSConnection.Get = ROSConnection.instance;
            ros.RegisterPublisher<StringMsg>(topicName);
        }

        void Update()
        {
            timeElapsed += Time.deltaTime;
            if (timeElapsed > publishMessageFrequency)
            {
                StringMsg stringMsg = new StringMsg("Hello from Unity!");
                ros.Publish(topicName, stringMsg);
                Debug.Log("Published: " + stringMsg.data);
                timeElapsed = 0;
            }
        }
    }
    ```

This opens up the possibility of developing your robot's logic in ROS 2 and visualizing/simulating its behavior in Unity, or even training AI agents in Unity and deploying them on real robots via ROS 2.
