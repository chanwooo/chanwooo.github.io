**/etc/sudoers** 파일을 잘못 저장하면 아주아주 곤란해진다

sudo 를 통해 권한을 받았는데 그 권한을 관리하는 파일이기에 편집을 하다가 문제가 있는채로 저장을 하게되면 다시는 편집할 수 없게되는 불상사가 일어나기 때문이다.



> sudo vi /etc/sudoers

...



sudoers파일에 뭔가 오타가 있는상태로 저장을 했더니 다음과같은 에러메시지를 뱉고 sudo는 먹통이되었다.

> \>>> /etc/sudoers: syntax error near line 31 <<<
>
> sudo: parse error in /etc/sudoers near line 31
>
> sudo: no valid sudoers sources found, quitting
>
> sudo: unable to initialize policy plugin

아주 난감하다 -_-;;



검색을 해보니 어렵지 않게 해결방법을 찾을 수 있었다.

> pkexec visudo

잘못된 부분을 수정한 뒤 잘 확인하고 저장을 하도록 하면 다시 sudo명령을 사용할 수 있게 된다.

시스템 중요 파일들은 저장하기전에 **두번 확인하여** 당황하는일이 없도록 하자!

