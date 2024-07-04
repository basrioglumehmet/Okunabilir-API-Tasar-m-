
# Okunabilir API Tasarımı

Okunabilir API, tüm geliştiriciler için son derece önemlidir. Projeye yeni bir geliştirici dahil olduğunda, diğer geliştiricilerin API'yi içgüdüsel olarak anlaması ve kolayca entegre edebilmesi gerekmektedir. Ayrıca, isimlendirmeler üzerinden geliştirici ekip arkadaşlarınızın API'nin ne iş yaptığını kavrayabilmesi önemlidir.

## Yapılmaması Gerekenler

Aksiyon ifadelerinden kaçınılmalıdır. Örneğin, get işlemi için `getUser` gibi bir endpoint kullanımı yanlıştır. Zaten HTTP verb'ler (GET, POST, PUT, DELETE vb.) API'lerin hangi eylemleri yaptıklarını anlatmaktadır. Basit düşünülmeli ve endpointlerin çoğul olarak tanımlanması gerekmektedir.

## Örnek Tablo

| HTTP Verb | Yanlış Kullanım        | Doğru Kullanım     |
|-----------|------------------------|--------------------|
| GET       | /getUser               | /users             |
| POST      | /createUser            | /users             |
| PUT       | /updateUser/{id}       | /users/{id}        |
| DELETE    | /deleteUser/{id}       | /users/{id}        |

### Detaylı Açıklamalar

- **GET /users**: Tüm kullanıcıları listeler. İsimlendirmede `get` gibi aksiyon ifadelerine gerek yoktur, HTTP verb zaten işlemi belirtmektedir.
- **POST /users**: Yeni bir kullanıcı oluşturur. `createUser` yerine sadece `/users` endpoint'i kullanmak daha doğrudur.
- **PUT /users/{id}**: Belirli bir kullanıcıyı günceller. `updateUser/{id}` yerine `/users/{id}` endpoint'i tercih edilmelidir.
- **DELETE /users/{id}**: Belirli bir kullanıcıyı siler. `deleteUser/{id}` yerine `/users/{id}` endpoint'i kullanılmalıdır.

Bu basit kurallar ve isimlendirme stratejileri, API'nizin okunabilirliğini ve anlaşılabilirliğini artıracak, böylece geliştirici ekip arkadaşlarınızın işini kolaylaştıracaktır. Okunabilir ve tutarlı bir API tasarımı, projelerin sürdürülebilirliği ve bakım kolaylığı açısından kritik öneme sahiptir.
