https://docs.unity3d.com/ja/current/ScriptReference/StateMachineBehaviour.html

# MonoBehaviourと呼び出される順番

## 最初の1F
- Awake()
- Start()
- FixedUpdate()
- Update()
- OnStateEnter()
- OnStateMove()
- LateUpdate()

## それ以降
- FixedUpdate() 
- Update() 
- OnStateExit() 
- OnStateUpdate() 
- OnStateMove() 
- OnStateIK() 
- LateUpdate() 


## 各コールバックが呼ばれるタイミング
### OnStateEnter()
そのStateに移行した時一番最初に呼ばれる

### OnStateUpdate()
OnStateEnter()の次のフレームから最後のExitを除いた毎フレーム呼ばれる  
Stateがトランジションしてる時でも呼ばれる

### OnStateMove()
Stateが切り替わるまで最初のフレームから最後のフレームまでずっと呼ばれる  
Stateがトランジションしてる時でも呼ばれる

### OnStateIK()
アニメーションがIKを更新した際だけ呼ばれる

### OnStateExit()
Stateの最後の1Fで呼ばれる
