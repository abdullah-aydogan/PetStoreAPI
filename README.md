# Petstore API Test Automation

Bu proje, [Swagger Petstore API](https://petstore.swagger.io/)'si üzerinde uçtan uca (E2E) veri bütünlüğünü ve CRUD işlemlerini doğrulamak amacıyla hazırlanmış bir test otomasyon mimarisidir.

## 🛠 Teknoloji Yığını

* **API Test Aracı:** Postman / Newman
* **Raporlama:** Allure Framework
* **Sürekli Entegrasyon (CI/CD):** GitHub Actions
* **Paket Yöneticisi:** npm (Node.js)

## 🏗 Proje Mimarisi (Chaining)

Test senaryoları birbirine bağlı (chaining) bir iş akışı şeklinde tasarlanmıştır:

1. **POST:** Yeni bir evcil hayvan (pet) kaydı oluşturulur ve dönen `id` dinamik olarak ortam değişkenine atanır.
2. **GET:** Oluşturulan `id` ile kayıt çağrılır ve veri doğruluğu (Assertion) test edilir.
3. **PUT:** Mevcut kaydın statüsü güncellenir (örn: `available` -> `sold`).
4. **DELETE:** Test sonrası temizlik (Teardown) amacıyla kayıt sistemden silinir.
5. **GET (Negatif):** Silinen verinin gerçekten sistemde olmadığı (`404 Not Found`) doğrulanır.

## 🚀 Kurulum

Projeyi yerel macOS veya benzeri terminal ortamınızda çalıştırmak için aşağıdaki adımları izleyin:

1. **Repoyu klonlayın:**
   ```bash
   git clone https://github.com/abdullah-aydogan/PetStoreAPI.git
   cd PetStoreAPI
   ```

2. **Bağımlılıkları yükleyin:**
   ```bash
   npm install
   ```

## ⚙️ Çalıştırma ve Raporlama

Testleri komut satırı üzerinden çalıştırmak için package.json içindeki npm scriptlerini kullanabilirsiniz:

**Testleri Koşmak İçin:**
```bash
npm run test
```

**Allure Raporunu Görüntülemek İçin:**
```bash
npm run report
```

## 🔄 CI/CD (GitHub Actions)

Bu proje, her `push` ve `pull_request` işleminde GitHub Actions üzerinden otomatik olarak çalışacak şekilde yapılandırılmıştır. Test sonuçları Allure raporu olarak oluşturulur ve **GitHub Pages** üzerinde canlı olarak yayınlanır.

---

**Yazar:** Abdullah Aydoğan
