
<pre>include와 lib 차이
헤더 파일(.h)이 들어가는 곳, 라이브러리 파일이 들어가는 곳

- 대표적인 버퍼 문제 -
  <code>
  #include <stdio.h>
    int main(){
    char string[20];
    char c;
    scanf("%s", string);
    scanf("%c", &c);
    printf("%s\n", string);
    printf("!!%c!!\n", c);
    return 0;
    }
  </code>

  - scanf("%s", string); 에서 마지막 널문자가 버퍼에 남아 다음 scanf인 scanf("%c", &c)가 영향을 받는다.
  

- scanf 패턴 문제 -
  #include <stdio.h>
  #include "student.h"

  int main(int argc, char *argv[]){
      struct student rec;
      FILE *fp;
      if (argc != 2)
      {
          fprintf(stderr, "사용법: %s 파일이름\n", argv[0]);
          return 1;
      }
      fp = fopen(argv[1], "w");
      printf("%-9s %-7s %-4s\n", "학번", "이름", "점수");
      while (fscanf(fp, "%d %s %d", &rec.id, rec.name, &rec.score) == 3)  ** // **
          printf("%10d %6s %6d\n", rec.id, rec.name, rec.score);
      fclose(fp);
      return 0;
  }

    ** // ** 에서 scanf를 받은 횟수 만큼 숫자로 변환 되기에 "%d %s %d" 총 3번을 입력 받는다. 그렇기에 == 3이라는 조건이 만족이 되고
    만약 사용자가 입력을 3개보다 적게 받거나, 3개 초과로 받는다면 그 자리에서 반복문을 빠져나와, return 0에 의해 종료 된다.
    scanf로 받으면 받은 횟수지만, printf를 정수로 반환하면 문자열의 개수만큼 반환이 된다. 
      
   ex)int = n;
      n = printf("안녕하세요.") 

      n은 마지막 Null문자를 포함한 7로 반환되는걸 알 수 있다.
    
    
</pre>
