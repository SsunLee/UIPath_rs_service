# UIPath_로봇관제시스템 자동화 WEB 

<br/><br/>

추가 기능 테스트 개발 예정 
- 로그인 / 로그아웃 반복 Test 
- 로봇 제어 반복 Test (대기장소 -> 충전장소)
- 컨텐츠 업로드 반복 Test 
- 요구사항 존재 시 개발 가능
- 테스트 결과 Excel로 결과 저장
- PASS/FAIL 여부 확정

<br/>


## 🐥 UI Path - Main Flow


### 🐣 Flow Chart  

![image](https://user-images.githubusercontent.com/41108401/120099808-8a921d80-c178-11eb-98cc-a5bde4d58b2a.png)

<br/>

### 🐣 Flow Description  

아래 표의 Flow 대로 구현 함.

<table>
    <tr>
        <th>Main</th>
        <th>Activity</th>
        <th>Description</th>                
    </tr>
    <tr>
        <td rowspan = "5">ID/PW -> OTP Requst</td>
        <td>Open Browser</td>
        <td> "https://kic-rs.lgerobot.com/rome" </td>                        
    </tr>    
    <tr>
        <td>Type ID</td>
        <td> "rsdp_op_app@yopmail.com" </td>                       
    </tr>    
    <tr>
        <td>Type PW</td>
        <td> Get Password(PW 암호화)</td>                          
    </tr>    
    <tr>
        <td>Request OTP</td>
        <td> 요청버튼 </td>                           
    </tr>            
    <tr>
        <td>Close Popup</td>
        <td> 요청팝업 '닫기' </td>                           
    </tr> <!-- End Flow Chart -->
    <tr>
        <td rowspan = "6"> GetOTP (OTP 얻기) </td>
        <td>Open Browser</td>
        <td> "http://www.yopmail.com/en/" </td>                        
    </tr>    
    <tr>
        <td>Type Input 'INPUT' ID</td>
        <td> "rsdp_op_app" </td>                       
    </tr>    
    <tr>
        <td>Click InBox</td>
        <td> 버튼 클릭 </td>                          
    </tr>    
    <tr>
        <td>Text Exists</td>
        <td> OTP 메일 있는지 찾기 </td>                           
    </tr>            
    <tr>
        <td>IF </td>
        <td>있다면 ? </td>                           
    </tr>       
     <tr>
        <td>SaveOTP To Variable</td>
        <td> 변수에 저장 </td>                           
    </tr> <!-- GetOTP (OTP 얻기)-->
    <tr>
        <td rowspan = "2"> IF OTP IS EXIST? </td>
        <td>TRUE</td>
        <td> 호출 [OTP 입력 -> 로그인] </td>                        
    </tr>
    <tr>
        <td > FALSE </td>
        <td> ROBOT IS STOP </td>                        
    </tr> <!-- End IF OTP IS EXIST-->
    <tr>
        <td rowspan = "3"> OTP 입력 -> 로그인인 </td>
        <td> Attach Browser</td>
        <td> 원래 브라우저 복귀 </td>                        
    </tr>
    <tr>
        <td > Type INPUT 'OTP' </td>
        <td> OTP 입력 </td>
    </tr>    
    <tr>
        <td > Click 'BUTTON' </td>
        <td> 버튼 클릭</td>
    </tr>        
<table/>
    
<br/>
    
### 🐣 시연 영상
https://user-images.githubusercontent.com/41108401/120104588-19f6fb00-c190-11eb-80f8-21810b4d5040.mp4   

