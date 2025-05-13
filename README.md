
def topla(sayi1, sayi2):
    return sayi1 + sayi2
def cikar(sayi1, sayi2):
    return sayi1 - sayi2
def carp(sayi1, sayi2):
    return sayi1 * sayi2
def bol(sayi1, sayi2):
    if sayi2 == 0:
        return "Tanımsız (Bir sayıyı sıfıra bölemezsiniz)"
    return sayi1 / sayi2
def islem_secimi_goster():
    islemler = ["+", "-", "*", "/"]
    for islem in islemler:
        print(islem)
def kullanici_girdisi_al():
    islem = input("Yapmak istediğiniz işlem tipini seçiniz: ")
    sayi1 = int(input("Birinci sayıyı giriniz: "))
    sayi2 = int(input("İkinci sayıyı giriniz: "))
    return islem, sayi1, sayi2
def hesap_makinesi():
    islem_fonksiyonlari = {
        "+": topla,
        "-": cikar,
        "*": carp,
        "/": bol
    }
    devam = True
    while devam:
        islem_secimi_goster()
        secilen_islem, sayi1, sayi2 = kullanici_girdisi_al()
        
        if secilen_islem in islem_fonksiyonlari:
            sonuc = islem_fonksiyonlari[secilen_islem](sayi1, sayi2)
            print(f"{sayi1} {secilen_islem} {sayi2} = {sonuc}")
        else:
            print("Geçersiz işlem seçimi!")
        devam_mi = input("Yeni bir işlem yapmak istiyor musunuz? ('Evet' ya da 'Hayır'): ")
        if devam_mi.lower() != "evet":
            devam = False
hesap_makinesi()
