# P2P
P2P API 
## 1 소개  
### 1.1 P2P자금관리
P2P금융기업이 대출 중개 시 투자자로부터 받은 투자금을 P2P금융기업의 자산과 분리하여 관리하기 위한 서비스입니다.
#### 1.1.1 P2P자금관리 오픈API 목록
| 전문명 | API |
|:---:|:---:|
| P2P투자자 및 차입자 가상계좌 발급 |	P2PNVirtualAccountNumberRequest |
| P2P 투자금 지급지시 | P2PNInvestmentPaymentOrder |
| P2P 투자금 지급결과 조회	| P2PNInvestmentLoanExecutionResultInquiry |
| P2P 입금확인 목록조회	| P2PNAccountReceiveInformationList |
| P2P 원리금상환	| P2PNInterestRepayment |
| P2P 원리금 입금결과 확인 |	P2PNInterestPaymentAccountReceiveResultConfirmation |
| P2P 투자예치금 반환 요청 |	P2PNInvestmentDepositAmountReturn |
| P2P 투자예치금 반환 결과 조회 |	P2PNInvestmentDepositAmountReturnResultList |
		 	 
## 2 resource url
#### 2.1 P2P투자자 및 차입자 가상계좌 발급
https://developers.nonghyup.com/P2PNVirtualAccountNumberRequest.nh
#### 2.2 P2P 투자금 지급지시
https://developers.nonghyup.com/P2PNInvestmentPaymentOrder.nh
#### 2.3 P2P 투자금 지급결과 조회
https://developers.nonghyup.com/P2PNInvestmentLoanExecutionResultInquiry.nhh
#### 2.4 P2P 입금확인 목록조회
https://developers.nonghyup.com/P2PNAccountReceiveInformationList.nh 
#### 2.5 P2P 원리금상환
https://developers.nonghyup.com/P2PNInterestRepayment.nh
#### 2.6 P2P 원리금 입금결과 확인
https://developers.nonghyup.com/P2PNInterestPaymentAccountReceiveResultConfirmation.nh
#### 2.7 P2P 투자예치금 반환 요청
https://developers.nonghyup.com/P2PNInvestmentDepositAmountReturn.nh
#### 2.8 P2P 투자예치금 반환 결과 조회
https://developers.nonghyup.com/P2PNInvestmentDepositAmountReturnResultList.nh

## 3 example
### 3.1.1 투자금관리용 가상계좌발급 Request example
```json
{
    "Header": {
        "ApiNm": "P2PNVirtualAccountNumberRequest",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "13E_001_00",
        "IsTuno": "123243240",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "P2PCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "P2PVractUsg": "1",
    "InvstBrwNm": "홍길동"
}
```
### 3.1.2 투자금관리용 가상계좌발급 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| P2PVractUsg |	P2P가상계좌 구분코드 |	필드 |	1 |	필수 |	1:투자자용, 2:차입자용 |
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| InvstBrwNm |	투자자및차입자명 |	필드 |	50 |	필수 |	- MAX: 한글 6자리 - 예금주명 앞에 기관 약어명(3자) 자동추가 (총 9자리) |
### 3.1.3 투자금관리용 가상계좌발급 Response example
```json
{
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "P2PNVirtualAccountNumberRequest",
        "IsTuno": "123243240",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "13E_001_00"
    },
    "P2PCmtmNo": "0000000000",
    "P2PVractUsg": "1",
    "Vran": "79000000000081",
    "ChidSqno": "0000000000",
    "InvstBrwNm": "홍길동"
}
```
### 3.1.4 투자금관리용 가상계좌발급 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	 
| P2PVractUsg |	P2P가상계좌 | 구분코드 |	필드 |	1 |	필수 |	 
| InvstBrwNm |	투자자및차입자명 |	필드 |	50 |	필수 |	

### 3.2.1 입금확인 목록조회 Request example
```json
{
    "Header": {
        "ApiNm": "P2PNAccountReceiveInformationList",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "13E_001_00",
        "IsTuno": "123445",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "Vran": "79000000000075",
    "Iqds": "1",
    "Insymd": "20191212",
    "Ineymd": "20191212",
    "PageNo": "1"
}
```
### 3.2.2 입금확인 목록조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| Vran |	가상계좌번호 |	필드 |	20 |	선택 |	가상계좌 입력 시 해당 가상계좌의 내역 조회 |
| Iqds |	조회구분 |	필드 |	1 |	필수 |	1 : 일별, 2 :월별 |
| Insymd |	조회시작일자 |	필드 |	8 |	필수 |	현재일자 이후 조회 불가 -YYYYMMDD 또는 YYYYMM |
| Ineymd |	조회종료일자 |	필드 |	8 |	필수 |	현재일자 이후 조회 불가 -YYYYMMDD 또는 YYYYMM - 조회 범위 90 또는 3개월 이내 |
| PageNo |	페이지번호 |	필드 |	4 |	선택 |	Default : 1 |
### 3.2.3 입금확인 목록조회 Response example
```json
{
    "Header": {
      "Trtm": "112428",
      "Rsms": "정상처리 되었습니다.",
      "ApiNm": "P2PNAccountReceiveInformationList",
      "IsTuno": "123445",
      "Tsymd": "20191212",
      "FintechApsno": "001",
      "Iscd": "000013",
      "Rpcd": "00000",
      "ApiSvcCd": "13E_001_00"
      },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "UseAblAmt": "4899930000",
    "ThdDepsAmt": "100050000",
    "TotCnt": "2",
    "PageNo": "1",
    "Iqtcnt": "2",
    "REC": [
    {
        "Vran": "79000000000075",
        "RcvAmt": "10000",
        "Sqno": "00000000000004",
        "RcvYmd": "20191212"
    },
    {
        "Vran": "79000000000075",
        "RcvAmt": "100000000",
        "Sqno": "00000000000002",
        "RcvYmd": "20191212"
    }
    ]
}
```
### 3.2.4 입금확인 목록조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| UseAblAmt |	이용가능금액 |	필드 |	15 |	필수 |	사용가능 예치 금액 (가상계좌 집금 시간 전까지의 예치 금액 – 집금은 16시, 23시45분등 하루에 2번 발생한다.) |
| ThdDepsAmt |	금일예치금액 |	필드 |	15 |	필수 |	금일 예치 금액 |
| TotCnt |	총건수 |	필드 |	10 |	필수 |	 
| Iqtcnt |	조회총건수 |	필드 |	10 |	필수 |	 
| PageNo |	페이지번호 |	필드 |	4 |	필수 |	 
| REC |	거래내역목록 | 반복부 | | 필수 | 페이지당 20 건 |
| Sqno |	순번 |	필드 |	14 |	필수 |	 
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	 
| RcvYmd |	입금일자 |	필드 |	8 |	필수 |	YYYYMMDD |
| RcvAmt |	입금금액 |	필드 |	15 |	필수 |	 

### 3.3.1 투자금 지급지시 Request example
```json
{
    "Header": {
      "ApiNm": "P2PNInvestmentPaymentOrder",
      "Tsymd": "20191212",
      "Trtm": "112428",
      "Iscd": "000013",
      "FintechApsno": "001",
      "ApiSvcCd": "13E_001_00",
      "IsTuno": "000011233213",
      "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
      },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "SlctAmt": "1000000000",
    "LonTrm": "12",
    "InvSumAmt": "1000000000",
    "NewTrnsYn": "Y",
    "LoanNo": "123465432",
    "Bncd": "011",
    "BrwAcno": "3020000000150",
    "Dpnm": "홍길동",
    "LonApcYmd": "20191212",
    "DractOtlt": "출금계좌인자내용",
    "MractOtlt": "입금계좌인자내용",
    "Rec": [{
      "Vran": "79000000000074",
      "InvAmt": "1000000000"
    }]
}
```
### 3.3.2 투자금 지급지시 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| SlctAmt |	모집 금액 |	필드 |	15 |	필수 |	총 대출 금액 |
| LonTrm |	대출기간 |	필드 |	3 |	필수 |	개월 수 | (1년일 경우 "12") |
| InvSumAmt |	투자합계금액 |	필드 |	15 |	필수 |	반복부에 등록된 투자금액의 합계 |
| NewTrnsYn |	신규거래여부 |	필드 |	1 |	필수 |	신규 대출 : Y. 기존 대출 : N(차입자 계좌번호가 변경될 경우 N 거래 불가, 신규 대출번호로 전송) |
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	기관에서 채번하는 대출 고유 번호 (오픈플랫폼과 통신시에 사용하는 번호로 업체에서 관리하는 대출번호가 아님) |
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| BrwAcno |	차입자계좌번호 |	필드 |	20 |	필수 |	 
| Dpnm |	예금주명 |	필드 |	50 |	필수 |	 
| LonApcYmd |	대출신청일자 |	필드 |	8 |	필수 |	yyyymmdd |
| DractOtlt |	출금계좌인자내용 |	필드 |	12 |	필수 |	대부업자회사 투자용 계좌에 입력될 인자 내용 |
| MractOtlt |	입금계좌인자내용 |	필드 |	14 |	선택 |	차입자 계좌에 입력될 인자 내용 |
| Rec |	 	| 반복부 | | | 500 건으로 제한 / 합계 금액 10억으로 제한 |
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	투자자 가상계좌번호 |
| InvAmt |	투자금액 |	필드 |	15 |	필수 |	 
### 3.3.3 투자금 지급지시 Response example
```json
{   
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "P2PNInvestmentPaymentOrder",
        "IsTuno": "000011233213",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "13E_001_00"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "InvAccAmt": "1000000000",
    "InvSumAmt": "1000000000"   
}
```
### 3.3.4 투자금 지급지시 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	 
| InvAccAmt |	누적투자금액 |	필드 |	15 |	필수 |	해당 대출번호에 대한 누적 투자 금액 |
| InvSumAmt |	투자합계금액 |	필드 |	15 |	필수 |	입력부 레코드의 투자 금액 합계 |

### 3.4.1 투자금 지급결과조회 Request example
```json
{
    "Header": {
        "ApiNm": "P2PNInvestmentLoanExecutionResultInquiry",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "13E_001_00",
        "IsTuno": "123432",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "OrtrYmd": "20191212",
    "OrtrIsTuno": "000011233213"
}
```
### 3.4.2 투자금 지급결과조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	조회 할 고유 대출번호 |
| OrtrYmd |	원거래일자 |	필드 |	8 |	필수 |	원 거래의 API 실행일자 |
| OrtrIsTuno |	원거래기관거래고유번호 |	필드 |	20 |	필수 |	원 거래의 기관거래고유번호 |
### 3.4.3 투자금 지급결과조회 Response example
```json
{
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "P2PNInvestmentLoanExecutionResultInquiry",
        "IsTuno": "123432",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "13E_001_00"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "Pcrs": "00000",
    "Prtm": "200356"
}
```
### 3.4.4 투자금 지급결과조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	 
| Pcrs |	처리결과 |	필드 |	5 |	필수 |	원거래에 대한 처리결과 ※공통부 Rpcd=‘00000’경우만 참조 처리 결과 코드 |
| Prtm |	처리시각 |	필드 |	6 |	필수 |	투자금 지급이 처리된 시각 |

### 3.5.1 투자원리금상환 Request example
```json
{
    "Header": {
      "ApiNm": "P2PNInterestRepayment",
      "Tsymd": "20191212",
      "Trtm": "112428",
      "Iscd": "000013",
      "FintechApsno": "001",
      "ApiSvcCd": "13E_001_00",
      "IsTuno": "117688567532387",
      "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
      },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "Vran": "79000000000076",
    "RpaySumAmt": "100000000",
    "RpayYmd": "20191212",
    "DractOtlt": "출금계좌인자내용",
    "MractOtlt": "입금계좌인자내용",
    "Rec":[ {
      "Vran": "79000000000074",
      "RpayAmt": "100000000"
    }]
}
```
### 3.5.2 투자원리금상환 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 | 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	기관에서 채번하는 대출 고유 번호 |
| RpaySumAmt |	상환합계금액 |	필드 |	15 |	필수 |	반복부 상환 금액의 합계 |
| RpayYmd |	상환일자 |	필드 |	8 |	필수 |	상환일자(API 호출 일자 : 금일) |
| DractOtlt |	출금계좌인자내용 |	필드 |	12 |	선택 |	대부업자회사 계좌에서 출금시 계좌에 입력될 인자내용 |
| MractOtlt |	입금계좌인자내용 |	필드 |	14 |	선택 |	 
| Rec |	| 반복부 | | | 500 건으로 제한 / 합계 금액 10억으로 제한 |
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	 
| RpayAmt |	상환금액 |	필드 |	15 |	필수 | 가상계좌 별 상환된 금액 |
### 3.5.3 투자원리금상환 Response example
```json
{
	"Header": {
	    "Trtm": "112428",
	    "Rsms": "정상처리 되었습니다.",
	    "ApiNm": "P2PNInterestRepayment",
	    "IsTuno": "117688567532387",
	    "Tsymd": "20191212",
	    "FintechApsno": "001",
	    "Iscd": "000013",
	    "Rpcd": "00000",
	    "ApiSvcCd": "13E_001_00"
	}
}
```
### 3.5.4 투자원리금상환 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 

### 3.6.1 투자원리금 입금결과조회 Request example
```json
{
    "Header": {
        "ApiNm": "P2PNInterestPaymentAccountReceiveResultConfirmation",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "13E_001_00",
        "IsTuno": "329742398",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "OrtrYmd": "20191212",
    "OrtrIsTuno": "117688567532387"
}
```
### 3.6.2 투자원리금 입금결과조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	조회 할 대출 고유 번호 |
| OrtrYmd |	원거래일자 |	필드 |	8 |	필수 |	원 거래의 API 실행일자 |
| OrtrIsTuno |	원거래기관거래고유번호 |	필드 |	20 |	필수 |	원 거래의 기관거래고유번호 |
### 3.6.3 투자원리금 입금결과조회 Response example
```json
{
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "P2PNInterestPaymentAccountReceiveResultConfirmation",
        "IsTuno": "329742398",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "13E_001_00"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "LoanNo": "123465432",
    "Pcrs": "00000",
    "Prtm": "201027"
}
```
### 3.6.4 투자원리금 입금결과조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| LoanNo |	대출번호 |	필드 |	13 |	필수 |	 
| Pcrs |	처리결과 |	필드 |	5 |	필수 |	원거래에 대한 처리결과※공통부 Rpcd=‘00000’경우만 참조처리 결과 코드 |
| Prtm |	처리시각 |	필드 |	6 |	필수 |	 

### 3.7.1 투자예치금 반환요청 Request example
```json
{
  "Header": {
    "ApiNm": "P2PNInvestmentDepositAmountReturn",
    "Tsymd": "20191212",
    "Trtm": "112428",
    "Iscd": "000013",
    "FintechApsno": "001",
    "ApiSvcCd": "13E_001_00",
    "IsTuno": "324234234324",
    "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
  },
  "P2pCmtmNo": "0000000000",
  "ChidSqno": "0000000000",
  "Vran": "79000000000074",
  "RtnAmt": "100000000",
  "Bncd": "011",
  "Dpnm": "홍길동",
  "IvstrAcct": "3020000000150",
  "MractOtlt": "입금계좌인자내용"
}
```
### 3.7.2 투자예치금 반환요청 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	 
| RtnAmt |	반환금액 |	필드 |	15 |	필수 |	 
| Bncd |	은행코드 |	필드 |	3 |	필수 |	 
| Dpnm |	예금주명 |	필드 |	50 |	필수 |	 
| IvstrAcct |	투자자계좌번호 |	필드 |	20 |	필수 |	 
| MractOtlt |	입금계좌인자내용 |	필드 |	14 |	필수 |	차입자 계좌에 입력될 인자 내용 |
### 3.7.3 투자예치금 반환요청 Response example
```json
{
	"Header": {
	    "Trtm": "112428",
	    "Rsms": "정상처리 되었습니다.",
	    "ApiNm": "P2PNInvestmentDepositAmountReturn",
	    "IsTuno": "324234234324",
	    "Tsymd": "20191212",
	    "FintechApsno": "001",
	    "Iscd": "000013",
	    "Rpcd": "00000",
	    "ApiSvcCd": "13E_001_00"
	}
}
```
### 3.7.4 투자예치금 반환요청 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 

### 3.8.1 투자예치금 반환결과조회 Request example
```json
{
    "Header": {
        "ApiNm": "P2PNInvestmentDepositAmountReturnResultList",
        "Tsymd": "20191212",
        "Trtm": "112428",
        "Iscd": "000013",
        "FintechApsno": "001",
        "ApiSvcCd": "13E_001_00",
        "IsTuno": "2130832759",
        "AccessToken": "10b74dd7f5f0f521ecdc7ade82f793bdfc119c3635d2e5303ae6aba0c93d4246"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "Vran": "79000000000074",
    "OrtrYmd": "20191212",
    "OrtrIsTuno": "324234234324"
}
```
### 3.8.2 투자예치금 반환결과조회 Request Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	  	
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| Vran |	가상계좌번호 |	필드 |	20 |	필수 |	 
| OrtrYmd |	원거래일자 |	필드 |	8 |	필수 |	 
| OrtrIsTuno |	원거래기관거래고유번호 |	필드 |	20 |	필수 |
### 3.8.3 투자예치금 반환결과조회 Response example
```json
{
    "Header": {
        "Trtm": "112428",
        "Rsms": "정상처리 되었습니다.",
        "ApiNm": "P2PNInvestmentDepositAmountReturnResultList",
        "IsTuno": "2130832759",
        "Tsymd": "20191212",
        "FintechApsno": "001",
        "Iscd": "000013",
        "Rpcd": "00000",
        "ApiSvcCd": "13E_001_00"
    },
    "P2pCmtmNo": "0000000000",
    "ChidSqno": "0000000000",
    "Pcrs": "00000",
    "Prtm": "201337"
    }
```
### 3.8.4 투자예치금 반환결과조회 Response Element
| Element |	한글명 | Type |	Length |	optional |	Description |  
|:---|:---:|:---:|:---:|:---:|:---|  
| Header || 공통부 |||||	 
| P2pCmtmNo |	P2P약정번호 |	필드 |	20 |	필수 |	 
| ChidSqno |	자회사일련번호 |	필드 |	20 |	필수 |	 
| Pcrs |	처리결과 |	필드 |	5 |	필수 |	원거래에 대한 처리결과※공통부 Rpcd=‘00000’경우만 참조처리 결과 코드 |
| Prtm |	처리시각 |	필드 |	6 |	필수 |	 
