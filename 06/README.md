```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Testing : MonoBehaviour
{
    private void Start()
    {                
        /*
        int i = 0;
        while(i < 3)
        {
            i++;
            Debug.Log(i);
        }
        */
        
        /*
        int i = 0;
        do {
          i++;
          Debug.Log(i);
        } while(i<3);
        */
        
        /*
        char[] charArray = new char[]{'a', 'b', 'c', 'd', 'e'};
        for(int i = 0; i < charArray.Length; i++)
        {
            Debug.Log(i + ": " + charArray[i]);
        }
        */
        
        /*
        char[] charArray = new char[]{'a', 'b', 'c', 'd', 'e'};
        foreach(char c in charArray)
        {
            Debug.Log(c);
        }
        */
        
        /*
        List<char> charList = new List<char>{'a', 'b', 'c', 'd', 'e'};
        foreach(char c in charList)
        {
            Debug.Log(c);
        }
        */
        
        /*
        List<char> charList = new List<char>{'a', 'b', 'c', 'd', 'e'};
        for(int i = 0; i < charList.Count; i++)
        {
            Debug.Log(i + ": " + charList[i]);
            if(charList[i]=='b')
            {
            	charList.RemoveAt(i);
            	i--;
            }
        }
        */
        
        /*
        List<char> charList = new List<char>{'a', 'b', 'c', 'd', 'e'};
        foreach(char c in charList)
        {
            // if(c == 'b') continue;
            if(c == 'b') break;
            Debug.Log(c);
        }
        */
        
        int width = 2;
        int height = 3;
        for(int x = 0; x < width; x++)
            // if(x==1) break;
            for(int y = 0; y < height; y++)
            {
                if(y==1) break;
                Debug.Log(x + ", " + y);
            }
    }
}
```

