using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Firethrower : MonoBehaviour
{
    [SerializeField] float damage = 5, startTime=0, endTime=0;
    [SerializeField] ParticleSystem[] fire = new ParticleSystem[4];
    Life playerLife=null;
    BlindEffect effectBlind=null;
    float timer = 0; 
    bool isOn = false;
    float timer1 = 0;
    bool count = false;

    private void Start()
    {
        difficulty();

    }
    void Update()
    {
        turningOn();
        Timer1();
    }
    void Timer1()
    {
        if (count == true)
        {
            timer1 += Time.deltaTime;
        }

        if (timer1 >= 5)
        {
            effectBlind.effect = false;
            count = false;
            timer1 = 0;
        }
    }
    void turningOn()
    {
        timer += Time.deltaTime;
        if (timer >= startTime && timer <= endTime){
            isOn = true;
            if (fire[1].isPlaying == false){
                for (int i = 0; i < 4; i++){
                    fire[i].Play();
                }
            }
        }
        else if (timer >= endTime){
            for (int i = 0; i < 4; i++){
                fire[i].Stop();
            }
            isOn = false;
            timer = 0;
        }
    }
    void OnTriggerStay(Collider other)
    {
        if (isOn && other.gameObject.CompareTag("Player"))
        {
            effectBlind = other.gameObject.GetComponent<BlindEffect>();
            effectBlind.effect = true;
            count = false;
        }
    }
    /*{
        if (isOn && other.gameObject.CompareTag("Player")){
            playerLife = other.gameObject.GetComponent<Life>();
            playerLife.life -= damage * Time.deltaTime;
            playerLife.playHurt();
        }
    }*/
    private void OnTriggerExit(Collider other)
    {

        if (other.gameObject.CompareTag("Player"))
        {
            count = true;
        }
    }
    void difficulty(){
        if (DifficultySelector.dificultSelector == 0){
            Easy();
        }
        else if (DifficultySelector.dificultSelector == 2){
            Hard();
        }
    }
    void Easy(){
        damage = damage / 2;
    }
    void Hard(){
        damage = damage * 2;
    }
}
