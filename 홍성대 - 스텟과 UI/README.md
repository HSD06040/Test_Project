//대충 스텟 클래스

[Header("Stat")]
public int damage {get; private set;}
public int maxHP {get; private set;}

private int curHP;
public int currentHealth
{
	get => curHP;	

	set
	{
		curHP = value;
		OnChangedHealth?.Invoke(curHP);
	}
}

public event Action<int> OnChangedHealth;

//대충 UI 클래스

public Text text;

text.text = curHP;
