## Inventory Structure/Model/Define
Ansible은 직접적으로 노드를 지정하여 컨트롤하는 경우는 흔하지 않습니다.
Ansible의 인벤토리 시스템을 사용하면 호스트를 그룹으로 정리할 수 있으며, 
이를 사용하여 특정 호스트 세트에서 구성을 적용하거나 작업을 실행할 수 있습니다. <br>

Ansible 인벤토리의 강력한 기능 중 하나는 그룹 계층을 만들 수 있는 기능으로, 그룹을 다른 그룹 내에 중첩할 수 있습니다. 
이 계층 구조는 복잡한 환경을 관리하고 Ansible 플레이북을 확장 가능하고 유지 관리하기 쉽게 만드는 데 도움이 될 수 있습니다.

### 각 노드
```
  - node100 : dev - front + backend
  - node200 : dev - back
  
  - node300 : e2e - front + backend
  - node400 : e2e - backend

```

-----
### DEV 노드
아래의 정의는 DEV환경을 제한적으로만 계층적으로 구룹핑한것입니다. 
아래의 정의는 DEV환경내의 Front서비스와 Backend서비스에대한 Target을 정의합니다.

```
DEV FRONT SERVICE
  - node100

DEV BACKEND SERVICE
  - node100
  - node200

DEV_BOTH_SERVICE
  - node100
  - node200

```

### E2E 노드
아래의 정의는 E2E환경을 제한적으로만 계층적으로 구룹핑한것입니다.
아래의 정의는 E2E환경내의 Front서비스와 Backend서비스에대한 Target을 정의합니다.
```
E2E FRONT SERVICE
  - node300

E2E BACKEND SERVICE
  - node300
  - node400

E2E BOTH_SERVICE
  - node300
  - node400

```

-----
### 서비스 종류별 노드 Define
아래의 정의는 Maturity level에 상관없이 서비스 종류별로 (DEV와 E2E환경을 하위로하는)  계층적으로 구룹핑한것입니다.
```
FRONT SERVICE
  - node100
  - node300
  
BACKEND SERVICE
  - node100
  - node200
  - node300
  - node400
  
BOTH SERVICE
  - node100
  - node200
  - node300
  - node400
```

-----                  
### 서비스 종류별 노드 Define  ALL SERVICE
```
  - node100
  - node200
  - node300
  - node400
```



