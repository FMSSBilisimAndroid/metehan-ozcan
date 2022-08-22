### NameSpaces Nedir?
- Genel olarak, XML namespaces, öğe, nitelik adları arasında çakışma olmaması için kullanılır. XML dosyasında kullanılırlar.


- Namespaces, kodu/kitaplıkları benzersiz bir şekilde tanımlar. Aynı adları kullanan androide benzer api yazarsak, android api  ile kendi apimizi ayırt etmenin tek yolu namespaces kullanmaktır.


`xmlns:android=”http://schemas.android.com/apk/res/android `

`xmlns:android="http://schemas.android.com/tools"`

- Tanımladığımız bu namespacelerin adresine gitmeye çalıştığımızda bir şeye ulaşamayız.  Sebebi ise bu adreslerin, sadece android isim alanlarını tanımladığı içindir, URL değil URI (Birleşik Kaynak Tanımlayıcı), bu nedenle değeri sabittir, bir sabite eşdeğerdir.

- Bu uygulama derleme zamanında hataların işlenmesini kolaylaştırır ve eşsiz isim alanları tanımlayarak öğeler arasında çakışma olmasını engeller böylece uygulamaların daha yönetilebilir hale gelmesini sağlar.

- xmlns:Android isim alanı, Android platformu tarafından sağlanan özelliklere erişmek ve bunları kullanmak için kullanılır. Eğer namespace silinirse hiçbir özellik kullanılamaz.
- xmlns:app( veya xmlns:'customname') isim alanı, uygulama kapsamında tanımlanan özel niteliklere erişmek için kullanılır.
### Örnek
- Tools namespace yalnızca geliştirme aşamasında çalışır, geliştiricilere yardımcı olacak bir araç olarak düşünebiliriz. Sadece geliştirme aşamasında çalışır. Bir uygulama paketlendiğinde, tüm araç özellikleri atılır! Aşağıda bulunan kod parçasındaki gibi 


	`<Button`
		
	`style="@style/Widget.Material3.Button.TextButton"`
		
        android:layout_width="wrap_content"
	
        android:layout_height="wrap_content"
	
        android:layout_alignParentBottom="true"
	
        android:layout_centerHorizontal="true"
	
        tools:backgroundTint="@color/purple_700"
	
        android:backgroundTint="@color/black"
	
        android:text="test"
	
        android:textSize="16dp"
	
        app:layout_constraintBottom_toTopOf="@+id/imageView"
	
        app:layout_constraintEnd_toEndOf="parent"
	
        app:layout_constraintStart_toStartOf="parent"
	
        app:layout_constraintTop_toTopOf="parent"`


		
- tools:backgroundTint=Purple
- android:backgroundTint=black olarak ayarlağında

- Design kısmında butonumuz mor görünür. 

![1](https://user-images.githubusercontent.com/70481060/186033228-a3ec11f4-66a3-445c-b132-159173e1329f.png)



- Ancak paketlenirken bu atılacağı için emülatörde buton siyah görünecektir. Bu da namespace'in farklı kullanımlarından bir örneğidir.


![2](https://user-images.githubusercontent.com/70481060/186033245-1979f388-48d8-4a6b-b1cf-df446179c639.png)



