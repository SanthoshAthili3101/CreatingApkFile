Generated APK file for Android
s-1: keytool -genkey -v -keystore key.keystore -alias Name -keyalg RSA -keysize 2048 -validity 10000
s-2:  csproj (if project solution and project are in different directory)
    <PropertyGroup Condition="'$(TargetFramework.Contains(-android))' and '$(Configuration)' == 'Release'">
        <AndroidKeyStore>True</AndroidKeyStore>
        <AndroidSigningKeyStore>..\key.keystore</AndroidSigningKeyStore>
        <AndroidSigningStorePass>123456</AndroidSigningStorePass>
        <AndroidSigningKeyAlias>Name</AndroidSigningKeyAlias>
        <AndroidSigningKeyPass>123456</AndroidSigningKeyPass>
    </PropertyGroup>

    or

    s-2:  csproj (if project solution and project are in samr directory)
    <PropertyGroup Condition="'$(TargetFramework.Contains(-android))' and '$(Configuration)' == 'Release'">
        <AndroidKeyStore>True</AndroidKeyStore>
        <AndroidSigningKeyStore>key.keystore</AndroidSigningKeyStore>
        <AndroidSigningStorePass>123456</AndroidSigningStorePass>
        <AndroidSigningKeyAlias>Name</AndroidSigningKeyAlias>
        <AndroidSigningKeyPass>123456</AndroidSigningKeyPass>
    </PropertyGroup>
s-3: dotnet publish -c Release -f:net8.0-android

s-1 and s-3 needs to execute commands in terminal
