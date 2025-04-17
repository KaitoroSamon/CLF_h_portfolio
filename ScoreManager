using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.UI;
using UnityEngine.SceneManagement;

public class ScoreManager : MonoBehaviour
{
    public GameObject score_object = null;
    public int score_P1 = 0; //ここでPlayerの変数
    public int score_P2 = 0;
    public int score_P3 = 0;
    public int score_P4 = 0;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        Text score_text = score_object.GetComponent<Text> ();
        score_text.text = "kill:" + score_P1;

        if(Input.GetKeyDown(KeyCode.A))
        {    //ここに敵を倒した時の処理を入れると増える
            score_P1 += 1;  
        }
        if(Input.GetKeyDown(KeyCode.Space))
        {    //ただのscene移動
            SceneManager.LoadScene("Result") ;
        }

        SceneManager.sceneLoaded += KeepScore; 
    }
    void KeepScore(Scene next, LoadSceneMode mode)
    {
        var sm = GameObject.Find("ScoreManager").GetComponent<ScoreManager>();
        sm.score_P1 = score_P1;

        SceneManager.sceneLoaded -= KeepScore;
    }
}
