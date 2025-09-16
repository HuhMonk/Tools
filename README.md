<a href="https://discord.gg/8tuuGjuEE9"><img src="https://img.shields.io/badge/discord-brightgreen.svg?style=for-the-badge&logo=discord&colorA=23272a&colorB=7289da" alt="Discord!"></a>
# Tools
easier ways to use unity by using tools i made

# Future Plans
```cs
using Tools.Optimization;
using Tools.Scripts;
```

# Script Tools

make sure you have this at top of your script
```cs
using Tools.Scripts;
```

### Attributes

Preview Prefab : shows a texture of what prefab you assigned
```cs
[PreviewPrefab]
public GameObject Bullet;
```

ReadOnly : make so you cant edit it
```cs
[ReadOnly]
public string Hello = "Hi";
```

ShowIf : makes so you can or cant see a field depending on ShowIfTrue Value
```cs
public bool UseLimitedAmmo;
[ShowIf("UseLimitedAmmo", true)] // now it will show if UseLimitedAmmo is true else it wont show
public int Ammo;
```

ShowIfFilled : makes so you can see field if a specefic field is not null
```cs
public Transform Tip;

[ShowIfFilled("Tip")]
public GameObject BulletPrefab;
```

Editor Button : Adds a button at the buttom of your inspector to trigger a function when pressed
```cs
[EditorButton("Press to say hi")] // if label is not filled it will do Function/Method Name
void DebugHi() => Debug.Log("Hi");
```


### GameObject Extensions

GetOrAddComponent : makes so when you call that it will try find that compoenent on the gameobject if it cant find it it will be added onto the gameobject
```cs
void Start()
{
    Rigidbody rb = gameObject.GetOrAddComponent<Rigidbody>();
}
```

RandomChance : returns true if percent is higher then the generated number
```cs
void Start()
{
    if(RandomChance(25f))
    {
        Debug.Log("Jackpot Hit");
    }
}
```

RandomWeighted : gets a component from a list and has a chance of returning that using weights
```cs
void GetDrop()
{
    var loot = new List<string> {"Common", "Rare", "Epic"};
    var weights = new List<float> { 70f, 25f, 5f};
    string drop = Extensions.RandomWeighted(loot, weights);
}
```
