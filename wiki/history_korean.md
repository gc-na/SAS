# [운영 체제] C Shell (csh) history 사용법: 명령어 기록 보기

## Overview
`history` 명령어는 C Shell에서 사용자가 입력한 명령어의 기록을 보여줍니다. 이 명령어를 사용하면 이전에 실행한 명령어를 쉽게 확인하고 재사용할 수 있습니다.

## Usage
기본 구문은 다음과 같습니다:
```
history [options] [arguments]
```

## Common Options
- `-c`: 현재 세션의 명령어 기록을 지웁니다.
- `-r`: 기록 파일에서 명령어를 읽어옵니다.
- `-w`: 현재 세션의 명령어 기록을 파일에 저장합니다.

## Common Examples
- 최근 10개의 명령어 기록 보기:
  ```csh
  history 10
  ```

- 전체 명령어 기록 보기:
  ```csh
  history
  ```

- 명령어 기록을 파일에 저장하기:
  ```csh
  history -w
  ```

- 명령어 기록 지우기:
  ```csh
  history -c
  ```

## Tips
- 자주 사용하는 명령어는 `!n` 형식으로 입력하여 빠르게 실행할 수 있습니다. 여기서 `n`은 기록에서의 명령어 번호입니다.
- `history` 명령어를 정기적으로 사용하여 이전 명령어를 확인하고, 불필요한 명령어를 지워서 기록을 관리하세요.
- 기록을 파일에 저장하여 세션 간에 명령어를 유지할 수 있습니다.