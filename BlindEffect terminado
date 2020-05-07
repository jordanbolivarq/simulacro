using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class BlindEffect : MonoBehaviour
{
    float PlayerD;
    public bool effect;
    CharacterDamage characterDamage;
    Firethrower firethrower;
    [SerializeField] GameObject fireThrower;

    void Start()
    {
        characterDamage = gameObject.GetComponent<CharacterDamage>();
        PlayerD = characterDamage.pDamage;
        firethrower = fireThrower.GetComponent<Firethrower>();
    }

    void Update()
    {
        if (effect == true)
        {
            characterDamage.pDamage = 0;
            //Debug.Log(characterDamage.pDamage);
        }
        else
            characterDamage.pDamage = PlayerD;
        //Debug.Log(effect);
    }
}
