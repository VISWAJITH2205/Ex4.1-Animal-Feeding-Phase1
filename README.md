# Ex4.1-Animal-Feeding-Phase1

Aim:

To develop a animal feeding game-Phase-1 using unity.

Algorithm:

Player Control :

Step 1:
Extract the package and in unity, asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted

Step 2:
If you want, drag a different material from Course Library > Materials onto the Ground object

Step 3:
Drag 1 Human, 3 Animals, and 1 Food object into the Hierarchy

Step 4:
Rename the character "Player", then reposition the animals and food so you can see them

Step 5:
Adjust the XYZ scale of the food (2,2,2) so you can easily see it from above

Step 6:
Edit their speed values and test to see how it looks. Drag all three animals into the Prefabs folder, choosing "Original Prefab"

PROGRAM:

DEVELOPED BY: Viswajith Lalithram R.V

REG NO: 212224240187

PLAYER CONTROL:

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PLAYERCONTROLLER : MonoBehaviour
{
    public float horizontalInput;
    public float speed = 10.0f;
    public float xRange = 10.0f;
    public GameObject projectilePrefab;
    void Start()
    {
        
    }

    void Update()
    {
        if (transform.position.x < -xRange)
        {
            transform.position = new Vector3(-xRange, transform.position.y, transform.position.z);
        }
        if (transform.position.x > xRange)
        {
            transform.position = new Vector3(xRange, transform.position.y, transform.position.z);
        }
        horizontalInput = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * horizontalInput * Time.deltaTime * speed);

        if (Input.GetKeyDown(KeyCode.Space))
        {
            Instantiate(projectilePrefab, transform.position, projectilePrefab.transform.rotation);
        }
    }
}

```

MOVING FORWARD :

```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MOVEFORWARD : MonoBehaviour
{
    public float speed = 30.0f ;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(Vector3.forward * Time.deltaTime * speed);   
    }
}

```

OUTPUT :

![Alt text](<Assets/Screenshot 2025-05-09 131013.png>)

RESULT :

Animal feeding game PHASE-1 using unity is developed successfully......


