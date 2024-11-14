# Nexon Player Info Display

이 프로젝트는 Nexon의 `카트라이더 러쉬플러스` 게임을 위한 API를 사용하여 플레이어 정보를 조회하고 화면에 표시하는 웹 애플리케이션입니다. 플레이어 닉네임을 입력하면 해당 플레이어의 OUID를 검색하고, OUID를 사용하여 플레이어의 타이틀과 장비 정보를 조회합니다.

## 주요 기능

1. **플레이어 OUID 검색**: 입력된 닉네임을 기반으로 Nexon API를 호출하여 OUID를 검색합니다.
2. **타이틀 및 장비 정보 조회**: OUID를 사용해 Nexon API에서 플레이어의 타이틀과 장비 정보를 조회하고 화면에 표시합니다.
3. **사용자 인터페이스**: Tailwind CSS를 사용하여 반응형 인터페이스를 제공하며, 입력 필드와 검색 버튼을 통해 사용자가 쉽게 닉네임을 입력하고 검색할 수 있습니다.

## 파일 구성

- `Nexon_API_kartrush.html`: HTML 파일로, JavaScript와 Tailwind CSS를 사용해 Nexon API에 연결하여 플레이어 정보를 표시하는 메인 파일입니다.

## 사용 방법

1. **API 키 설정**:
   - HTML 파일에 포함된 Nexon API 호출에 실제 API 키를 입력해야 합니다.
   - `x-nxopen-api-key` 헤더의 값을 Nexon에서 발급받은 실제 API 키로 변경합니다.

2. **HTML 파일 열기**:
   - 수정된 `Nexon_API_kartrush.html` 파일을 브라우저에서 엽니다.

3. **플레이어 정보 검색**:
   - 화면의 입력란에 플레이어 닉네임을 입력하고 `Search` 버튼을 클릭하면 해당 플레이어의 OUID와 타이틀 및 장비 정보가 표시됩니다.

## 코드 설명

- **fetchOuid(racerName)**: Nexon API를 사용해 닉네임을 기반으로 OUID를 검색합니다. 오류 발생 시 메시지를 출력하고 `null`을 반환합니다.
- **fetchTitleAndEquipment(ouid)**: OUID를 기반으로 타이틀과 장비 정보를 조회하며, 성공적으로 정보를 받아오면 `displayTitleAndEquipment` 함수가 데이터를 화면에 표시합니다.
- **displayTitleAndEquipment(data)**: 받아온 데이터를 HTML 요소로 변환해 플레이어 정보 섹션에 표시합니다. 데이터가 없을 경우 "타이틀과 장비가 없습니다"라는 메시지를 출력합니다.
- **handleSearch()**: 사용자가 `Search` 버튼을 클릭했을 때 호출되며, 입력된 닉네임을 기반으로 OUID와 타이틀/장비 정보를 차례로 조회하여 화면에 표시합니다.

## 라이브러리

- **Tailwind CSS**: 반응형 레이아웃을 손쉽게 구축하기 위해 사용했습니다.

## 주의 사항

- **API 키 보안**: 실제 서비스에서는 API 키를 안전하게 보호하기 위한 방법을 적용해야 합니다.
- **CORS 문제**: Nexon API는 CORS 설정에 민감할 수 있으므로, 서버와 API 호출 시 CORS 정책을 확인하십시오.

## 라이선스

이 프로젝트는 MIT 라이선스에 따라 오픈 소스로 제공됩니다.
