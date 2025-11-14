# Ex.No: 10  Implementation of 2D/3D game -------------------
### DATE: 14-11-2025                                                                        
### REGISTER NUMBER : 212223240056
### AIM: 
To develop a game -------------------------in Unity 
### Algorithm:
```
1.
```  
### Program:
```
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float moveSpeed = 5f;
    public GameObject laserPrefab;
    public Transform firePoint;

    void Update()
    {
        float move = Input.GetAxisRaw("Horizontal");
        transform.position += new Vector3(move, 0, 0) * moveSpeed * Time.deltaTime;

        if (Input.GetKeyDown(KeyCode.Space))
            Shoot();
    }

    void Shoot()
    {
        Instantiate(laserPrefab, firePoint.position, Quaternion.identity);
    }
}




using UnityEngine;
using UnityEngine.UI;
using UnityEngine.SceneManagement;

public class GameManager : MonoBehaviour
{
    public int score = 0;
    public Text scoreText;
    public GameObject gameOverPanel;

    public void AddScore()
    {
        score++;
        scoreText.text = score.ToString();
    }

    public void GameOver()
    {
        gameOverPanel.SetActive(true);
        Time.timeScale = 0f;
    }

    public void RestartGame()
    {
        Time.timeScale = 1f;
        SceneManager.LoadScene(SceneManager.GetActiveScene().name);
    }
}



using UnityEngine;

public class InvaderMove : MonoBehaviour
{
    public float speed = 2f;

    void Update()
    {
        transform.position += Vector3.down * speed * Time.deltaTime;

        if (transform.position.y < -5f)
            Destroy(gameObject);
    }
}




using UnityEngine;

public class InvaderSpawner : MonoBehaviour
{
    public GameObject invaderPrefab;
    public float spawnRate = 2f;
    float timer = 0f;

    void Update()
    {
        timer += Time.deltaTime;

        if (timer >= spawnRate)
        {
            float xPos = Random.Range(-7f, 7f);
            Instantiate(invaderPrefab, new Vector3(xPos, 5f, 0), Quaternion.identity);
            timer = 0f;
        }
    }
}




using UnityEngine;

public class HitDetector : MonoBehaviour
{
    public GameManager gm;

    void Start()
    {
        gm = GameObject.FindGameObjectWithTag("Logic").GetComponent<GameManager>();
    }

    private void OnTriggerEnter2D(Collider2D other)
    {
        if (other.CompareTag("Enemy"))
        {
            gm.AddScore();
            Destroy(other.gameObject);
            Destroy(gameObject);
        }
    }
}





```
### Output:

![1e1819a0-17f7-4a81-9bfe-34eb9d8e7842](https://github.com/user-attachments/assets/b8a443b2-cac2-4cae-abc3-f9679cae31ae)


### Result:
Thus the game was developed using Unity and adopted _-----------AI technology.
