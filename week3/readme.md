- 실행 오류 3가지 -
    syntex 
    run time(exception)
    semantic
  
  semantic을 제외한 나머지는 컴파일로 잡을 수 있지만, semantic은 디버깅으로만 잡을 수 있음
  디버깅 - semantic을 잡을려고 디버깅 시도함


    directory
. - 디렉토리의 서브 폴더
.. - 디렉터리의 부모 폴더
/ - root 디렉터리(모든 디렉토리의 출발점)
~ - home 디렉터리 

path : 절대경로, 상대경로

    mkdir(make directory) 0319 - 0319폴더를 생성한다.

$ cat > test.txt
    123456789
    abcdefghi
    컨트롤 + d 
    = test.txt에 내용을 넣음( cat은 파일안에 내용을 넣음)

echo "내용입니다." >> file.txt
    = file.txt안에 "내용입니다."를 넣음

만약 파일이 없다면 >> 명령어를 넣어서 생성과 동시에 작성이 가능하고, > 는 파일을 생성하지 않지만 해당 지정 파일이 있다면 작성가능하고, 해당 파일 이름이 없는경우 삭제한다.   

cat test.txt
    = test.txt안의 내용을 보여줌

$ touch test2.txt
    = test2.txt에 아무것도 내용이 없는 파일을 만듬(만약 파일이 있는 거라면 타임스탬프가 해당 명령어를 쓴 시간으로 바뀜)    

ll /bin
    = 기본 실행 명령어들의 나열
    
ll /usr/bin 
    = 


2.pdf 9page
    
파일은 디렉토리에 속하고, 사용자는 각각의 그룹에 속한다. 그룹의 설정에 따라 접근 가능하거나, 접근 불가 할 수 있다.


ll 열면 
drwxr-xr-x 2 :
drwxr-x--- 6 :


한 디렉토리를 삭제 할려고 하면 안의 폴더를 모두 삭제하여야 디렉토리를 지울 수 있음
rmdir "디렉토리이름"

하지만 rm -r "디렉토리이름" 명령어를 실행시키면 앞에 제약 없이 모두 지울 수 있음
ex) rm -r empDir/ : emDir의 서브 폴더를 모두 삭제 한다.       




   14주차 과제 ls /usr/bin  을 치면 명령어가 나오는데 30개 써서 c언어로 만듬
    라인 - \n 개수,  글자 수, 
    
