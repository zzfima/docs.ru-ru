---
title: Практическое руководство. Хранение асимметричных ключей в контейнере ключей
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET Framework], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET Framework]
- encryption [.NET Framework], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: 6b703156b38f52513c86f7b2507ac6c185a9dd50
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155949"
---
# <a name="how-to-store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="afd74-102">Практическое руководство. Хранение асимметричных ключей в контейнере ключей</span><span class="sxs-lookup"><span data-stu-id="afd74-102">How to: Store Asymmetric Keys in a Key Container</span></span>
<span data-ttu-id="afd74-103">Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="afd74-103">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="afd74-104">Если необходимо хранить закрытый ключ, следует использовать для этого контейнер ключа.</span><span class="sxs-lookup"><span data-stu-id="afd74-104">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="afd74-105">Дополнительные сведения о контейнерах ключей см. в разделе [Общие сведения о контейнерах ключей RSA уровня компьютера и пользователя](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="afd74-105">For more information on key containers, see [Understanding Machine-Level and User-Level RSA Key Containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>  
  
### <a name="to-create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="afd74-106">Порядок создания асимметричного ключа и сохранения его в контейнере ключей</span><span class="sxs-lookup"><span data-stu-id="afd74-106">To create an asymmetric key and save it in a key container</span></span>  
  
1. <span data-ttu-id="afd74-107">Создайте новый экземпляр класса <xref:System.Security.Cryptography.CspParameters> и передайте имя, которое будет вызывать контейнер ключей, в поле <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="afd74-107">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>  
  
2. <span data-ttu-id="afd74-108">Создайте новый экземпляр класса, производного от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm> (обычно **RSACryptoServiceProvider** или **DSACryptoServiceProvider**) и передайте ранее созданный объект **CspParameters** в свой конструктор.</span><span class="sxs-lookup"><span data-stu-id="afd74-108">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
### <a name="to-delete-the-key-from-a-key-container"></a><span data-ttu-id="afd74-109">Порядок удаления ключа из контейнера ключей</span><span class="sxs-lookup"><span data-stu-id="afd74-109">To delete the key from a key container</span></span>  
  
1. <span data-ttu-id="afd74-110">Создайте новый экземпляр класса **CspParameters** и передайте имя, которое должно вызывать контейнер ключей, в поле **CspParameters.KeyContainerName**.</span><span class="sxs-lookup"><span data-stu-id="afd74-110">Create a new instance of a **CspParameters** class and pass the name that you want to call the key container to the **CspParameters.KeyContainerName** field.</span></span>  
  
2. <span data-ttu-id="afd74-111">Создайте новый экземпляр класса, производного от класса **AsymmetricAlgorithm** (обычно это **RSACryptoServiceProvider** или **DSACryptoServiceProvider**) и передайте ранее созданный объект **CspParameters** в его конструктор.</span><span class="sxs-lookup"><span data-stu-id="afd74-111">Create a new instance of a class that derives from the **AsymmetricAlgorithm** class (usually **RSACryptoServiceProvider** or **DSACryptoServiceProvider**) and pass the previously created **CspParameters** object to its constructor.</span></span>  
  
3. <span data-ttu-id="afd74-112">Установите для свойства **PersistKeyInCSP** класса, являющегося производным от **AsymmetricAlgorithm**, значение **false** (**False** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="afd74-112">Set the **PersistKeyInCSP** property of the class that derives from **AsymmetricAlgorithm** to **false** (**False** in Visual Basic).</span></span>  
  
4. <span data-ttu-id="afd74-113">Вызовите метод **Clear** класса, производного от **AsymmetricAlgorithm**.</span><span class="sxs-lookup"><span data-stu-id="afd74-113">Call the **Clear** method of the class that derives from **AsymmetricAlgorithm**.</span></span> <span data-ttu-id="afd74-114">Этот метод освобождает все ресурсы класса и очищает контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="afd74-114">This method releases all resources of the class and clears the key container.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afd74-115">Пример</span><span class="sxs-lookup"><span data-stu-id="afd74-115">Example</span></span>  
 <span data-ttu-id="afd74-116">В следующем примере показано, как создать асимметричный ключ, сохранить его в контейнере ключей, затем извлечь ключ и удалить его из контейнера.</span><span class="sxs-lookup"><span data-stu-id="afd74-116">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>  
  
 <span data-ttu-id="afd74-117">Обратите внимание, что код в методах `GenKey_SaveInContainer` и `GetKeyFromContainer` совпадает.</span><span class="sxs-lookup"><span data-stu-id="afd74-117">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span>  <span data-ttu-id="afd74-118">Если указать имя контейнера ключей для объекта <xref:System.Security.Cryptography.CspParameters> и передать его в объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>, когда свойство <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> или <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> имеет значение true, происходит следующее.</span><span class="sxs-lookup"><span data-stu-id="afd74-118">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to true, the following occurs.</span></span>  <span data-ttu-id="afd74-119">Если контейнер ключей с указанным именем не существует, он создается, а ключ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="afd74-119">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>  <span data-ttu-id="afd74-120">Если контейнер ключей с указанным именем существует, то ключ в этом контейнере автоматически загружается в текущий объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="afd74-120">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>  <span data-ttu-id="afd74-121">Таким образом, код в методе `GenKey_SaveInContainer` сохраняет ключ, так как он выполняется первым, а код в методе `GetKeyFromContainer` загружает ключ, так как он выполняется вторым.</span><span class="sxs-lookup"><span data-stu-id="afd74-121">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it is run second.</span></span>  
  
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
  
```console  
Key added to container:  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key retrieved from container :  
<RSAKeyValue> Key Information A</RSAKeyValue>  
Key deleted.  
Key added to container:  
<RSAKeyValue> Key Information B</RSAKeyValue>  
Key deleted.  
```  
  
## <a name="see-also"></a><span data-ttu-id="afd74-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afd74-122">See also</span></span>

- [<span data-ttu-id="afd74-123">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="afd74-123">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="afd74-124">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="afd74-124">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)
- [<span data-ttu-id="afd74-125">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="afd74-125">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="afd74-126">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="afd74-126">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
