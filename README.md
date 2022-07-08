# flutter_auth_firebase documentation

Documentation : https://firebase.flutter.dev/docs/overview

1. Install pubspec.yaml
​   - Tambah : flutter pub add firebase_auth
     link : https://pub.dev/packages/firebase_auth/install
  - Tambah : flutter pub add firebase_core
     link : https://pub.dev/packages/firebase_core/install
  - Tambah : flutter pub add google_fonts
     link : https://pub.dev/packages/google_fonts/install
  - Tambah : flutter pub add google_sign_in
     link : https://pub.dev/packages/google_sign_in/install

2. Daftar ke Firebase
  - Android Package Name 
    - Register App : 
      - Project flutter > android > app > build.gradle > applicationId > disini
  - App Nickname (optional)
    - My Android App :
      - (Nama Bebas)
  - Debug Signing Certificate SHA-1 (optional)
    - Wajib Mendaftarkan Keytool Pada Environment Variables
      - Cari Keytool Di Sini : C:\Program Files\Android\Android Studio\jre\bin\Keytool.exe
    - Daftarkan User Variables For AdityaAgusWisanto > Path > Edit > Tambahkan Disini > C:\Program Files\Android\Android Studio\jre\bin\Keytool.exe
    - Ketik Perintah Pada Terminal PROJECT FLUTTER : 
      - keytool -list -v -alias androiddebugkey -keystore C:\Users\AdityaAgusWisanto\.android\debug.keystore
      - Masukkan password defaultnya yaitu : android
      - Enter Keystore password : android
      - Copy SHA1 taruh project pada awal pendaftaran firebase dan Copy SHA256 pada firebase project overview > your apps > Copy SHA256 disini
      - Add Firebase SDK (Tambahin Sesuai Prosedur Firebase) dan Cari Setup Untuk Menunjang Kebutuhan pubspec.yaml pada build.gradle
        - tambahin : dependencies > com.google.firebase:firebase-auth, platform('com.google.firebase:firebase-bom:30.0.1')
      - Download google-services.json
      - Copy google-services.json di : Project flutter > android > app > disini
  - Enable pada Authentification : Phone, Google, Anonymous, Email and Password
  - Tambahkan : WidgetsFlutterBinding.ensureInitialized(); , await Firebase.initializeApp(); pada void main() async
