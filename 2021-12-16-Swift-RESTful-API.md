# Swift RESTful API 호출을 배워보자!!!

### 우선 기본적인 호출을 위해 Playground 에서 API 호출을 해봤어요!!!

```swift
import Foundation

do {
    
    // Method : GET
    let url = URL(string: "https://newsapi.org/v2/everything?q=tesla&from=2021-11-16&sortBy=publishedAt&apiKey=8a74e2d7e6cb4c39a48f322f555895c9")
    
    // API 호출
    let response = try String (contentsOf: url!)
    
    print(response)
} catch {
    print(error.localizedDescription)
}


// 출력 결과 : 
//		{"status":"ok","totalResults":14534,"articles":[{"source":{"id":null,"name":"Motley Fool Australia"},"author":"Sebastian Bowen","title":"Meet DRIV (ASX:DRIV), the electric vehicle ETF that just listed on the ASX","description":"Meet the ASX's newest ETF!\nThe post Meet DRIV (ASX:DRIV), the electric vehicle ETF that just listed on the ASX appeared first on The Motley Fool Australia.","url":"https://www.fool.com.au/2021/12/16/meet-driv-asxdriv-the-electric-vehicle-etf-that-just-listed-on-the-asx/","urlToImage":"https://www.fool.com.au/wp-content/uploads/2021/04/self-drive.jpg","publishedAt":"2021-12-16T01:43:53Z","content":"The ASX boards have welcomed some new exchange-traded funds (ETFs) today. Yes, the BetaShares Electric Vehicles and Future Mobility ETF (ASX: DRIV) joins the share market. It lists alongside another … [+2339 chars]"},{"source":{"id":null,"name":"N-tv.de"},"author":"n-tv NACHRI 
```

### 위와 같이 방대한 양의 자료가 JSON 형식으로 전송되어졌음을 볼 수 있어요!!!



### \* API호출 방법 (반환 타입 설정)

 (**1)** **Base64인코딩 형식** : let response = try **Data**(contentsOf: url!)

  \* Base64 인코딩 : binary data -> ASCII format

​    이미지 데이터에 많이 사용 (binary데이터는 이동하다가 서버에서 1byte로 묶여서 데이터에 손실이 올 수 있기 때문)

 

 **(2)** **문자열 반환** : let response = try **String**(contentsOf: url!)



**(3) UTF-8인코딩 :** let response = try **NSString**(contentsOf: url!, encoding: String.Encoding.utf8.rawValue) 

   \* 한글과 같은 2byte를 사용하는 언어를 utf-8로 인코딩



