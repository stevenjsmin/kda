### Installation Playbooks
이 플래이북 구룹은 시스템 설정 및 변경, 라이브러리 설치, 어플리케이션 설치등의 플레이북 구룹입니다.


### Examples
-----

#### Ansible Role 생성
```
  $> ansible-galaxy init [ROLE_NAME]
  $> ansible-galaxy install [ROLE_NAME]
  $> ansible-galaxy install --roles-path [ROLE_DIR] [ROLE_NAME]
```

##### Ansible Playbook 실행

```
  $> ansible-playbook playbook.yml -v -t tomcat,java
  $> ansible-playbook playbook.yml -v -t tomcat,java -e tomcat_admin_password="1234"
  
  $> ## Option : -l SUBSET, --limit SUBSET
  $> ansible-playbook playbook.yml -v -t tomcat,java
  
  $> ansible-playbook playbook.yml -v -l dev_backend_service -t tomcat,java
  $> ansible-playbook playbook.yml -v -l dev_backend_service -t tomcat
```
<br>

##### Ansible 실행결과 살펴보기


### 새로운 Ansible롤 만들어서 테스트해보기

```
  $> ## 코드를 Git으로부터 변경대상 서버에 체크 아웃한다
  $> ansible-galaxy init checkout
  
  $> ## task/main.yaml 에 git ansible.builtin.git을 구현- [tag: always]
  $> ## playbook.yml를 playbook_1.yml복사
  
  $> ## 다음 명령어 테스트
  $> ansible-playbook playbook_1.yml -v -t tomcat,java
```


