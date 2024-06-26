grep은 특정 패턴을 가진 텍스트를 검색하는 용도로 사용
주어진 파일 또는 표준 입출력에서 패턴과 일치하는 모든 라인을 출력한다.
- `-i`: 대소문자를 구분하지 않고 검색합니다.
- `-r` 또는 `-R`: 디렉터리와 그 아래 모든 하위 디렉터리에서 재귀적으로 검색합니다.
- `-v`: 패턴과 일치하지 않는 라인을 출력합니다.
- `-E`: 확장 정규식을 사용하여 패턴을 지정합니다.
- `-n`: 매칭되는 라인의 번호를 함께 출력합니다.

find는 파일시스템에서 파일을 검색할때 사용
주어진 디렉토리 아래에서 파일을 찾거나, 특정 조건을 만족하는 파일을 검색할 수 있다.
- `-name`: 파일 이름을 기준으로 검색합니다.
- `-type`: 파일 타입을 지정하여 검색합니다. (f: 일반 파일, d: 디렉터리, l: 심볼릭 링크 등)
- `-mtime`: 파일의 최근 수정 시간을 기준으로 검색합니다.
- `-size`: 파일 크기를 기준으로 검색합니다.
- `-exec`: 검색된 파일에 대해 특정 명령을 실행합니다.

