stdin이 0

stdout이 1

stderr이 2

그다음으로 오는 파일이 3,4,5.. 이런식입니다.

  
ssize_t(data type) - 부호 있는 정수(signed)

size_t(data type) - 부호 있는 정수(0 ~ )

ex) - read() -

#include 

ssize_t read ( int fd, void *buf, size_t nbytes );

파일 읽기에 성공하면 읽은 바이트 수, 파일 끝을 만나면 0,

실패하면 -1을 반환한다.    

ㄴ해당 코드는 읽은 바이트 수를 사용하기 떄문에 1부터 다른 정수까지 return을 시킬 수 있다. 만약 실패하면 1로 반환한다 치면 중복 리턴이 올 수 있기 때문에 음수에 해당하는 ssize_t를 사용하여
  실패하면 -1로 반환하게 한다.

-  fsize.c -

#include 

#include 

#include 

#include 

#define BUFSIZE 1024

/* 파일 크기를 계산 한다 */

int main(int argc, char *argv[])

{

char buffer[BUFSIZE];

int fd;

ssize_t nread;

long total = 0;

if ((fd = open(argv[1], O_RDONLY)) == -1)

perror(argv[1]);

/* 파일의 끝에 도달할 때까지 반복해서 읽으면서 파일 크기 계산 */

while( (nread = read(fd, buffer, BUFSIZE)) > 0) // nread는 파일을 읽었으면 1 반환

total += nread; // 총 읽은 파일 개수

close(fd);

printf ("%s 파일 크기 : %ld 바이트 \n", argv[1], total);

exit(0);

}

- write() -

#include 

ssize_t write (int fd, void *buf, size_t nbytes);

파일에 쓰기를 성공하면 실제 쓰여진 바이트 수를 반환하고,

실패하면 -1을 반환한다.

ㄴ fd에 buf에 들어있는 nbytes길이 만큼 보냄. 하지만 쓰기에 실패한다면 -1을 반환함
