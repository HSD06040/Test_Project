// 플레이어_컨트롤러
 
 [SerializeField] private Rigidbody rigid;
 [SerializeField] private float playerSpeed;
 [SerializeField] private int playerHealth;
 
 private Vector3 inputVec;
 
 void Update()
 {
     PlayerInput();
 }
 private void FixedUpdate()
 {
     Move();
 }
 private void PlayerInput()
 {
     float x = Input.GetAxis("Horizontal");
     float z = Input.GetAxis("Vertical");
     inputVec = new Vector3(x, 0, z).normalized;
 }
 private void Move()
 {
     rigid.velocity = inputVec * playerSpeed;
 }