Acelerador
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class SpeedTrigger : MonoBehaviour
{
public float speedFactor = 2.5f;
void OnTriggerEnter(Collider other)
{
    other.GetComponent<FirstPersonMovement>().runSpeed *= speedFactor;
}
void OnTriggerExit(Collider other)
{
     other.GetComponent<FirstPersonMovement>().runSpeed /= speedFactor;
}
}
Trampolin
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class JumpTrigger : MonoBehaviour
{
public float bounce = 5f;
private void OnCollisionEnter(Collision other)
{
    if (other.gameObject.CompareTag("Player")){

        other.gameObject.GetComponent<Rigidbody>().AddForce(Vector3.up * bounce, ForceMode.Impulse);
    }
     
}
}
Trampa
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEditor.SceneManagement;

public class SceneChange : MonoBehaviour
{
 
  
   private void OnTriggerEnter(Collider collision)
  {
    EditorSceneManager.LoadScene("Level_1");
  }
  
}
Portal Magico
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Teleport : MonoBehaviour
{
  public Transform teleportPoint;

  void OnTriggerEnter(Collider other)
  {
    other.GetComponent<Transform>().position = teleportPoint.position;
  }
}
