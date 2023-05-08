
#include <stdio.h>
// Binary Search fonksiyonu
int binarySearch(int arr[], int l, int r, int x) {
	// arama işlemini gerçekleştir
    while (l <= r) {
    	//orta noktayı bul
        int m = l + (r - l) / 2;
        // eğer aranan eleman orta noktaysa, orta noktanın indeksini döndür
        if (arr[m] == x)
            return m;
            // eğer aranan eleman orta noktadan büyükse, arama işlemini sağ tarafta sürdür
        if (arr[m] < x)
            l = m + 1;
            // eğer arana eleman orta noktadan küçükse, arama işlemini sol tarafta sürdür
        else
            r = m - 1;
    }
    // eğer aranan eleman bulunamadıysa -1 döndür
    return -1;
}

int main(void) {
	// sıralanmış dizi
    int arr[] = {3, 4, 8, 9, 24, 47, 68, 76, 84};
    // dizinin boyutunu bul
    int n = sizeof(arr) / sizeof(arr[0]);
    // aranacak eleman
    int x = 47;
    // Binary Search fonksiyonunu çağır ve sonucu result değişkenine ata
    int result = binarySearch(arr, 0, n - 1, x);
    // eğer sonuç -1 ise eleman bulunamadı demektir. ekrana mesaj yazdır
    if(result == -1)
        printf("eleman indexte mevcut değil");
        // eğer sonuç -1 değilse eleman bulundu demektir. elemanın indeksini ekrana yazdırır
    else
        printf("eleman indexte mevcut %d", result);
    return 0;
}
