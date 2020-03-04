---
title: Шифрование данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 669b9c77ca0102ed94d8743cf37b18c0d0c528dc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159407"
---
# <a name="encrypting-data"></a><span data-ttu-id="15819-102">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="15819-102">Encrypting Data</span></span>
<span data-ttu-id="15819-103">Симметричное и асимметричное шифрования выполняются с использованием различных процессов.</span><span class="sxs-lookup"><span data-stu-id="15819-103">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="15819-104">Симметричное шифрование выполняется в рамках потоков, поэтому его удобно применять для шифрования больших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="15819-104">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="15819-105">Асимметричное шифрование выполняется в рамках небольшого числа байтов, поэтому его удобно применять для шифрования только небольших объемов данных.</span><span class="sxs-lookup"><span data-stu-id="15819-105">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="15819-106">Симметричное шифрование</span><span class="sxs-lookup"><span data-stu-id="15819-106">Symmetric Encryption</span></span>  
 <span data-ttu-id="15819-107">Управляемые классы симметричного шифрования используются со специальным классом потока <xref:System.Security.Cryptography.CryptoStream> , который шифрует данные, считанные в поток.</span><span class="sxs-lookup"><span data-stu-id="15819-107">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="15819-108">Класс **CryptoStream** инициализируется при помощи управляемого класса потока, класса, реализующего интерфейс <xref:System.Security.Cryptography.ICryptoTransform> (созданный из класса, который реализует алгоритм шифрования), и перечисления <xref:System.Security.Cryptography.CryptoStreamMode> , описывающего разрешенный тип доступа для **CryptoStream**.</span><span class="sxs-lookup"><span data-stu-id="15819-108">The **CryptoStream** class is initialized with a managed stream class, a class implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="15819-109">Класс **CryptoStream** может быть инициализирован при помощи любого класса, производного от класса <xref:System.IO.Stream> , включая <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>и <xref:System.Net.Sockets.NetworkStream>.</span><span class="sxs-lookup"><span data-stu-id="15819-109">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="15819-110">При помощи этих классов можно осуществлять симметричное шифрование для различных объектов потока.</span><span class="sxs-lookup"><span data-stu-id="15819-110">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
 <span data-ttu-id="15819-111">В следующем примере показано, как создать новый экземпляр класса <xref:System.Security.Cryptography.RijndaelManaged> , который реализует алгоритм шифрования Rijndael, и использовать его для шифрования класса **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="15819-111">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class, which implements the Rijndael encryption algorithm, and use it to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="15819-112">В этом примере **CryptoStream** инициализируется при помощи объекта потока `myStream` , который может быть любым типом управляемого потока.</span><span class="sxs-lookup"><span data-stu-id="15819-112">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="15819-113">В метод **CreateEncryptor** из класса **RijndaelManaged** передается ключ и вектор инициализации, используемые для шифрования.</span><span class="sxs-lookup"><span data-stu-id="15819-113">The **CreateEncryptor** method from the **RijndaelManaged** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="15819-114">В этом случае используется ключ и вектор инициализации по умолчанию, созданные из `rmCrypto` .</span><span class="sxs-lookup"><span data-stu-id="15819-114">In this case, the default key and IV generated from `rmCrypto` are used.</span></span> <span data-ttu-id="15819-115">Наконец, передается **CryptoStreamMode.Write** , указывая доступ на запись к потоку.</span><span class="sxs-lookup"><span data-stu-id="15819-115">Finally, the **CryptoStreamMode.Write** is passed, specifying write access to the stream.</span></span>  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 <span data-ttu-id="15819-116">После выполнения этого кода все данные, записанные в объект **CryptoStream** , шифруются при помощи алгоритма Rijndael.</span><span class="sxs-lookup"><span data-stu-id="15819-116">After this code is executed, any data written to the **CryptoStream** object is encrypted using the Rijndael algorithm.</span></span>  
  
 <span data-ttu-id="15819-117">В следующем примере показан весь процесс создания потока, шифрования потока, чтения из потока и закрытия потока.</span><span class="sxs-lookup"><span data-stu-id="15819-117">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="15819-118">Этот пример создает сетевой поток, который шифруется при помощи класса **CryptoStream** и класса **RijndaelManaged** .</span><span class="sxs-lookup"><span data-stu-id="15819-118">This example creates a network stream that is encrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="15819-119">Сообщение записывается в зашифрованный поток при помощи класса <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="15819-119">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15819-120">Этот пример также можно использовать для записи в файл.</span><span class="sxs-lookup"><span data-stu-id="15819-120">You can also use this example to write to a file.</span></span> <span data-ttu-id="15819-121">Чтобы сделать это, удалите ссылку <xref:System.Net.Sockets.TcpClient> и замените <xref:System.Net.Sockets.NetworkStream> на <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="15819-121">To do that, delete the <xref:System.Net.Sockets.TcpClient> reference and replace the <xref:System.Net.Sockets.NetworkStream> with a <xref:System.IO.FileStream>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the
      'listening process.
      Dim tcp As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.
      Dim netStream As NetworkStream = tcp.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim rmCrypto As New RijndaelManaged()  
  
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt
      'it with the Rijndael class.  
      Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the
      'network stream.  
      Dim sWriter As New StreamWriter(cryptStream)  
  
      'Write to the stream.  
      sWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      sWriter.Close()  
      cryptStream.Close()  
      netStream.Close()  
      tcp.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the
         //listening process.
         TcpClient tcp = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.
         NetworkStream netStream = tcp.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged rmCrypto = new RijndaelManaged();  
  
         byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt
         //it with the Rijndael class.  
         CryptoStream cryptStream = new CryptoStream(netStream,
         rmCrypto.CreateEncryptor(key, iv),
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the
         //network stream.  
         StreamWriter sWriter = new StreamWriter(cryptStream);  
  
         //Write to the stream.  
         sWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         sWriter.Close();  
         cryptStream.Close();  
         netStream.Close();  
         tcp.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 <span data-ttu-id="15819-122">В предыдущем примере для успешного выполнения должен присутствовать процесс, прослушивающий IP-адрес и номер порта, указанные в классе <xref:System.Net.Sockets.TcpClient> .</span><span class="sxs-lookup"><span data-stu-id="15819-122">For the previous example to execute successfully, there must be a process listening on the IP address and port number specified in the <xref:System.Net.Sockets.TcpClient> class.</span></span> <span data-ttu-id="15819-123">Если прослушивающий процесс существует, код будет подключаться к нему, шифровать поток при помощи симметричного алгоритма Rijndael и записывать фразу "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="15819-123">If a listening process exists, the code will connect to the listening process, encrypt the stream using the Rijndael symmetric algorithm, and write "Hello World!"</span></span> <span data-ttu-id="15819-124">в этот поток.</span><span class="sxs-lookup"><span data-stu-id="15819-124">to the stream.</span></span> <span data-ttu-id="15819-125">При успешном выполнении код выводит в консоли следующий текст:</span><span class="sxs-lookup"><span data-stu-id="15819-125">If the code is successful, it displays the following text to the console:</span></span>  
  
```console  
The message was sent.  
```  
  
 <span data-ttu-id="15819-126">Однако если указанный прослушивающий процесс отсутствует или возникает исключение, код отображает в консоли следующий текст:</span><span class="sxs-lookup"><span data-stu-id="15819-126">However, if no listening process is found or an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a><span data-ttu-id="15819-127">Асимметричное шифрование</span><span class="sxs-lookup"><span data-stu-id="15819-127">Asymmetric Encryption</span></span>  
 <span data-ttu-id="15819-128">Асимметричные алгоритмы обычно используются для шифрования малых объемов данных, например для шифрования симметричного ключа и вектора инициализации.</span><span class="sxs-lookup"><span data-stu-id="15819-128">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="15819-129">Как правило, сторона, осуществляющая асимметричное шифрование, использует открытый ключ, созданный другой стороной.</span><span class="sxs-lookup"><span data-stu-id="15819-129">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="15819-130">Для этих целей платформа .NET Framework предоставляет класс <xref:System.Security.Cryptography.RSACryptoServiceProvider> .</span><span class="sxs-lookup"><span data-stu-id="15819-130">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is provided by the .NET Framework for this purpose.</span></span>  
  
 <span data-ttu-id="15819-131">В следующем примере сведения об открытом ключе используются для шифрования симметричного ключа и вектора инициализации.</span><span class="sxs-lookup"><span data-stu-id="15819-131">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="15819-132">Инициализируются два массива байтов, представляющих открытый ключ третьей стороны.</span><span class="sxs-lookup"><span data-stu-id="15819-132">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="15819-133">Объект <xref:System.Security.Cryptography.RSAParameters> инициализируется с этими значениями.</span><span class="sxs-lookup"><span data-stu-id="15819-133">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="15819-134">Далее объект **RSAParameters** (вместе с представляемым им открытым ключом) импортируется в **RSACryptoServiceProvider** при помощи метода <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="15819-134">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSACryptoServiceProvider** using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="15819-135">Наконец, выполняется шифрование закрытого ключа и вектора инициализации, созданных классом <xref:System.Security.Cryptography.RijndaelManaged> .</span><span class="sxs-lookup"><span data-stu-id="15819-135">Finally, the private key and IV created by a <xref:System.Security.Cryptography.RijndaelManaged> class are encrypted.</span></span> <span data-ttu-id="15819-136">В этом примере требуется, чтобы в системе было установлено 128-битное шифрование.</span><span class="sxs-lookup"><span data-stu-id="15819-136">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim publicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte  
        Dim encryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim rsa As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()  
  
        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = publicKey  
        rsaKeyInfo.Exponent = exponent  
  
        'Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(RM.Key, False)  
        encryptedSymmetricIV = rsa.Encrypt(RM.IV, False)  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Security.Cryptography;  
  
class Class1  
{  
   static void Main()  
   {  
      //Initialize the byte arrays to the public key information.  
      byte[] publicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] encryptedSymmetricKey;  
      byte[] encryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters rsaKeyInfo = new RSAParameters();  
  
      //Set rsaKeyInfo to the public key values.
      rsaKeyInfo.Modulus = publicKey;  
      rsaKeyInfo.Exponent = exponent;  
  
      //Import key parameters into RSA.  
      rsa.ImportParameters(rsaKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged rm = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      encryptedSymmetricKey = rsa.Encrypt(rm.Key, false);  
      encryptedSymmetricIV = rsa.Encrypt(rm.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="15819-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15819-137">See also</span></span>

- [<span data-ttu-id="15819-138">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="15819-138">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="15819-139">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="15819-139">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="15819-140">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="15819-140">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
