---
title: "How to: Store Asymmetric Keys in a Key Container | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "cryptography [.NET Framework], asymmetric keys"
  - "storing asymmetric keys"
  - "keys, asymmetric"
  - "encryption keys"
  - "keys, storing in key containers"
  - "asymmetric keys [.NET Framework]"
  - "encryption [.NET Framework], asymmetric keys"
  - "decryption keys"
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
caps.latest.revision: 20
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# How to: Store Asymmetric Keys in a Key Container
Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере.  Если необходимо хранить закрытый ключ, следует использовать для этого контейнер ключа.  Дополнительные сведения о контейнерах ключей см. в разделе [Understanding Machine\-Level and User\-Level RSA Key Containers](../Topic/Understanding%20Machine-Level%20and%20User-Level%20RSA%20Key%20Containers.md).  
  
### Порядок создания асимметричного ключа и сохранения его в контейнере ключей  
  
1.  Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters> и передайте имя, которое должно вызывать контейнер ключей, в поле <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=fullName>.  
  
2.  Создайте новый экземпляр класса, производного от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm> \(обычно это **RSACryptoServiceProvider** или **DSACryptoServiceProvider**\) и передайте ранее созданный объект **CspParameters** в его конструктор.  
  
### Порядок удаления ключа из контейнера ключей  
  
1.  Создайте новый экземпляр класса **CspParameters** и передайте имя, которое должно вызывать контейнер ключей, в поле **CspParameters.KeyContainerName**.  
  
2.  Создайте новый экземпляр класса, производного от класса **AsymmetricAlgorithm** \(обычно это **RSACryptoServiceProvider** или **DSACryptoServiceProvider**\) и передайте ранее созданный объект **CspParameters** в его конструктор.  
  
3.  Установите для свойства **PersistKeyInCSP** класса, являющегося производным от **AsymmetricAlgorithm**, значение **false** \(**False** в Visual Basic\).  
  
4.  Вызовите метод **Clear** класса, производного от **AsymmetricAlgorithm**.  Этот метод освобождает все ресурсы класса и очищает контейнер ключей.  
  
## Пример  
 В следующем примере показано, как создать асимметричный ключ, сохранить его в контейнере ключей, затем извлечь ключ и удалить его из контейнера.  
  
 Обратите внимание, что код в методах `GenKey_SaveInContainer` и `GetKeyFromContainer` совпадает.  Если указать имя контейнера ключей для объекта <xref:System.Security.Cryptography.CspParameters> и передать его в объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>, когда свойство <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> или <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> имеет значение true, происходит следующее.  Если контейнер ключей с указанным именем не существует, он создается, а ключ сохраняется.  Если контейнер ключей с указанным именем существует, то ключ в этом контейнере автоматически загружается в текущий объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>.  Таким образом, код в методе `GenKey_SaveInContainer` сохраняет ключ, так как он выполняется первым, а код в методе `GetKeyFromContainer` загружает ключ, так как он выполняется вторым.  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
 _  
  
Public Class StoreKey  
  
    Public Shared Sub Main()  
        Try  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
  
            ' Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer")  
  
            ' Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer")  
        Catch e As CryptographicException  
            Console.WriteLine(e.Message)  
        End Try  
    End Sub  
  
    Public Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        ' name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key added to container:  {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub GetKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container MyKeyContainerName.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : {0}", rsa.ToXmlString(True))  
    End Sub  
  
    Public Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)  
        ' Create the CspParameters object and set the key container   
        '  name used to store the RSA key pair.  
        Dim cp As New CspParameters()  
        cp.KeyContainerName = ContainerName  
  
        ' Create a new instance of RSACryptoServiceProvider that accesses  
        ' the key container.  
        Dim rsa As New RSACryptoServiceProvider(cp)  
  
        ' Delete the key entry in the container.  
        rsa.PersistKeyInCsp = False  
  
        ' Call Clear to release resources and delete the key from the container.  
        rsa.Clear()  
  
        Console.WriteLine("Key deleted.")  
    End Sub  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
  
public class StoreKey  
  
{  
    public static void Main()  
    {  
        try  
        {  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Retrieve the key from the container.  
            GetKeyFromContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
  
            // Create a key and save it in a container.  
            GenKey_SaveInContainer("MyKeyContainer");  
  
            // Delete the key from the container.  
            DeleteKeyFromContainer("MyKeyContainer");  
        }  
        catch(CryptographicException e)  
        {  
            Console.WriteLine(e.Message);  
        }  
  
    }  
  
    public static void GenKey_SaveInContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key added to container: \n  {0}", rsa.ToXmlString(true));  
    }  
  
    public static void GetKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container MyKeyContainerName.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Display the key information to the console.  
        Console.WriteLine("Key retrieved from container : \n {0}", rsa.ToXmlString(true));  
    }  
  
    public static void DeleteKeyFromContainer(string ContainerName)  
    {  
        // Create the CspParameters object and set the key container   
        // name used to store the RSA key pair.  
        CspParameters cp = new CspParameters();  
        cp.KeyContainerName = ContainerName;  
  
        // Create a new instance of RSACryptoServiceProvider that accesses  
        // the key container.  
        RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(cp);  
  
        // Delete the key entry in the container.  
        rsa.PersistKeyInCsp = false;  
  
        // Call Clear to release resources and delete the key from the container.  
        rsa.Clear();  
  
        Console.WriteLine("Key deleted.");  
    }  
}  
```  
  
```Output  
  
            Ключ добавляется в контейнер:  
<RSAKeyValue> Информация о ключе А</RSAKeyValue>  
Ключ извлекается из контейнера:  
<RSAKeyValue> Информация о ключе А</RSAKeyValue>  
Ключ удаляется.  Ключ добавляется в контейнер:  
<RSAKeyValue> Информация о ключе Б</RSAKeyValue>  
Ключ удаляется.    
```  
  
## См. также  
 [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)   
 [Encrypting Data](../../../docs/standard/security/encrypting-data.md)   
 [Decrypting Data](../../../docs/standard/security/decrypting-data.md)   
 [Службы криптографии](../../../docs/standard/security/cryptographic-services.md)