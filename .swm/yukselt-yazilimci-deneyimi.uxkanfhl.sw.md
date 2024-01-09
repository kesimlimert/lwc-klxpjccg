---
title: Yukselt Yazilimci Deneyimi
---
Yukselt olarak Saleor kullanilmaktadir, bu sebeble [Yukselt Dashboard](https://yukselt.eu.saleor.cloud/dashboard?saleorPluginId=cloud_auth.CloudAuthorizationPlugin)' a ilgili rol ile giris yapmak gerekmektedir. Saleor, Staff grubu (Yazilimci ve Operator) ve Customer grubu (Turist/Gezgin) yonettigimiz ayrica anlik olarak uygulama ile ilgileri datalari realtime olarak tuttugumuz bir enviromenttir.

# Hesaplarin Olusturulmasi

### Hesap Cesitleri:&nbsp;

- Operator Hesabi - Dashboard' a tam erisimi vardir.
- Yazilimci Hesabi - Dashboard' a kisitli erisimi vardir.
- Musteri (Turists hesabi) - Dashboard' a erisimi yoktur

Yukselt'in operatorler ve yazilimcilar icin olusturmus oldugu siteye girerek sitede belirtilen roller (Operator, Yazilimci), ad soyad ve eposta adresinizi girerek Saleor tarafindan bir aktivasyon maili alirsiniz ve hesabiniz olusturulmus olur. Daha sonra  [Yukselt Dashboard](https://yukselt.eu.saleor.cloud/dashboard?saleorPluginId=cloud_auth.CloudAuthorizationPlugin)' a giris yapabilirsiniz.

# Konaklama Verilerinin Yukselt' e Yuklenmesi

### Otel Odasi Olusturmak

1. Dashboardda solda bulunan "Products" a tiklayin.
2. Sag ustte bulunan siyah "Create Products" butonuna tiklayin.
3. "Product Type" seceneklerinin icinden "Hotel Rooms" u secin.
4. Formda istenen oda ile ilgili yerleri doldurup sag altta bulunan "Save" butonuna basin.

### Aktivite Olusturmak

1. Dashboardda solda bulunan "Products" a tiklayin.
2. Sag ustte bulunan siyah "Create Products" butonuna tiklayin.
3. "Product Type" seceneklerinin icinden "Experiences" i secin.
4. Formda istenen aktivite ile ilgili yerleri doldurup sag altta bulunan "Save" butonuna basin.

*Dashboardda eklenen urunleri, ekledikten hemen sonra uygulamaya yansiyacaktir.*

# Yazilimci Hesabi Ile Musteri Hesabi Olustumak

1. Yukselt Saleor Dashboard' a giris yaptiktan sonra soldaki menude bulunan "Customers" ' a tiklayin.
2. Sag ustte bulunan siyah "Create Customer" butonuna tiklayin.
3. Formda gerekli bilgileri doldurduktan sonra sag alttaki "Save" butonuna tiklayin.

# Yukselt Sistemine Rezervasyon Bilgilerinin Ulastirilmasi

Her otelin rezervasyon bilgilerini takip edebilmemiz icin her bir otelin kendine ait API endpoint' u bulunmasi gerekmektedir. Bu endpoint' u Saleor Dashboard' da otel yaratilirken doldurulan forma eklenmelidir.

**Verinin ornek formati asagidaki gibidir:**

```javascript
 reservations: [
  {
    id: "resv_101",
    customerId: "cust_101",
    roomId: "room_101",
    checkIn: "2021-07-01T14:00:00Z",
    checkOut: "2021-07-05T11:00:00Z",
    notes: "Sea-facing room requested",
    guests: {
      adults: [
        {
          firstName: "John",
          lastName: "Doe",
        },
      ],
      children: [
        {
          firstName: "Junior",
          lastName: "Doe",
        },
      ],
    },
    customerDetails: {
      firstName: "John",
      lastName: "Doe",
      email: "johndoe@example.com",
      phone: "+123456789",
    },
    payment: {
      status: "Pending",
      amount: 1200,
      currency: "USD",
    },
  },
  {
    id: "resv_102",
    customerId: "cust_102",
    roomId: "room_102",
    checkIn: "2021-07-01T14:00:00Z",
    checkOut: "2021-07-05T11:00:00Z",
    notes: "Sea-facing room requested",
    guests: {
      adults: [
        {
          firstName: "John",
          lastName: "Doe",
        },
      ],
      children: [
        {
          firstName: "Junior",
          lastName: "Doe",
        },
      ],
    },
    customerDetails: {
      firstName: "John",
      lastName: "Doe",
      email: "johndoe@example.com",
      phone: "+123456789",
    },
    payment: {
      status: "Pending",
      amount: 1200,
      currency: "USD",
    },
  },
];
```

# Rezervasyonu bulunan kullanicinin test edilmesi

Oncelikle uygulamaya giris yapan musteri hesabinin telefon veya eposta adresinin yaratilan musteri hesabi ile eslesmesi gerekir. Eslesmesi durumunda giris yapalan musteri hesabi rezervasyonunu ve sunulan firsatin cep telefonuna mesaj ile bilgisini alir.

1. Kullanici mesajda gonderilen URL ile uygulamayi acar
2. URL icerisindeki bilgi ile kendine ait firsatlari ve rezervasyonunu goruntuler
3. Secimini yaptiktan sonra satin alima gitmeden once tekrar telefon dogrulamasi alir, dogrulamasiyla ayni zamanda kalici olarak Yukselt uygulamasinda hesabi olusturulur
4. Satin alimi gerceklestirir

Test sonrasinda satin alim Saleor dashboard uzerinden goruntulunebilir veya otomatik eposta alinabilir.

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBbHdjLWtseHBqY2NnJTNBJTNBa2VzaW1saW1lcnQ=" repo-name="lwc-klxpjccg"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
