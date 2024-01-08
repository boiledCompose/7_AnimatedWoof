<p>
  
  ## 스프링 애니메이션

  
  ### 스프링 애니메이션은 스프링력에 기반한 물리학 기반 애니메이션이다.   
  
  스프링력은 두 가지 속성을 기준으로 한다:   
  1. **감쇠비:** 스프링의 탄성   
  2. **강도 수준:** 스프링이 끝까지 이동하는 속도인 강성
> [!NOTE]
> 감쇠비가 높을수록 스프링이 원래 모양으로 돌아올 때 반동력이 강해진다.    
> 강도 수준이 높을수록 스프링이 원래 모양으로 더 빨리 돌아온다.

### 코드 적용
- `animateContentSize()` 함수는 크기 변경에 애니메이션을 적용하기 위해 사용된다.
  ```
    Column(
      modifier = Modifier
        .animateContentSize()
    )
  ```
- `animationSpec` 매개변수는 애니메이션의 타입을 지정하기 위해 사용된다. 지금은 spring을 적용하는 케이스다.
  ```
    Column(
      modifier = Modifier
        .animateContentSize(
          animationSpec = spring()
        )
    )
  ```
- `dampingRatio`와 `stiffness`는 각각 탄성과 강성을 나타낸다.   이 코드에선 반동력이 없고 강성이 적당히 쎈 애니메이션을 적용한다. 
  ```
    Column(
      modifier = Modifier
        .animateContentSize(
          animationSpec = spring(
            dampingRatio = Spring.DampingRatioNoBouncy,
            stiffness = Spring.StiffnessMedium
          )
        )
    )
  ```
  
</p>
