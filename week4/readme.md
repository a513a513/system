.vimrc에 관련 코드를 넣으면 파일을 만들떄 적용 그대로 환경 설정이 된다.

return 0은 정상적으로 종료 되었다는 보고 이고, return a는 정상적으로 종료되지 않았다는 보고 이다.

- .vimrc파일 내용 -

set number          " 줄 번호 표시

set relativenumber  " 상대 줄 번호 표시

set tabstop=4       " 탭 너비 4칸

set shiftwidth=4    " 자동 들여쓰기 너비 4칸

set expandtab       " 탭을 스페이스로 변환

set noautoindent    " 자동 들여쓰기 끄기

set nosmartindent   " 스마트 들여쓰기 끄기

syntax on           " 문법 강조
