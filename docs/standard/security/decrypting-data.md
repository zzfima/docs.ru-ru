---
title: Расшифровка данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET Framework], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 37194380d9f08d328f836bcb8648772348958768
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706244"
---
# <a name="decrypting-data"></a><span data-ttu-id="bc872-102">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="bc872-102">Decrypting Data</span></span>

<span data-ttu-id="bc872-103">Расшифровка представляет собой операцию, обратную операции шифрования.</span><span class="sxs-lookup"><span data-stu-id="bc872-103">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="bc872-104">Для шифрования с секретным ключом необходимо знать как ключ, так и вектор инициализации, которые использовались при шифровании данных.</span><span class="sxs-lookup"><span data-stu-id="bc872-104">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="bc872-105">Для шифрования с открытым ключом необходимо знать либо открытый ключ (если данные были зашифрованы при помощи закрытого ключа), либо закрытый ключ (если данные были зашифрованы при помощи открытого ключа).</span><span class="sxs-lookup"><span data-stu-id="bc872-105">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="bc872-106">Симметричная расшифровка</span><span class="sxs-lookup"><span data-stu-id="bc872-106">Symmetric Decryption</span></span>

<span data-ttu-id="bc872-107">Расшифровка данных, зашифрованных при помощи симметричных алгоритмов, похожа на процесс, используемый для шифрования данных при помощи симметричных алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="bc872-107">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="bc872-108">Класс <xref:System.Security.Cryptography.CryptoStream> используется с классами симметричного шифрования, предоставляемыми платформой .NET Framework, для расшифровки данных, считанных из любого управляемого объекта потока.</span><span class="sxs-lookup"><span data-stu-id="bc872-108">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by the .NET Framework to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="bc872-109">В следующем примере показано, как создать новый экземпляр класса <xref:System.Security.Cryptography.RijndaelManaged> и использовать его для расшифровки объекта <xref:System.Security.Cryptography.CryptoStream> .</span><span class="sxs-lookup"><span data-stu-id="bc872-109">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class and use it to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="bc872-110">Этот пример сначала создает новый экземпляр класса **RijndaelManaged** .</span><span class="sxs-lookup"><span data-stu-id="bc872-110">This example first creates a new instance of the **RijndaelManaged** class.</span></span> <span data-ttu-id="bc872-111">Затем он создает объект **CryptoStream** и инициализирует его значением управляемого потока, вызвавшего `myStream`.</span><span class="sxs-lookup"><span data-stu-id="bc872-111">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="bc872-112">Далее в метод **CreateDecryptor** из класса **RijndaelManaged** передается тот же ключ и вектор инициализации, которые использовались для шифрования, а затем метод передается в конструктор **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="bc872-112">Next, the **CreateDecryptor** method from the **RijndaelManaged** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span> <span data-ttu-id="bc872-113">Наконец, перечисление **CryptoStreamMode.Read** передается в конструктор **CryptoStream** , чтобы задать доступ на чтение для потока.</span><span class="sxs-lookup"><span data-stu-id="bc872-113">Finally, the **CryptoStreamMode.Read** enumeration is passed to the **CryptoStream** constructor to specify read access to the stream.</span></span>

```vb
Dim rmCrypto As New RijndaelManaged()
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateDecryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Read)
```

```csharp
RijndaelManaged rmCrypto = new RijndaelManaged();
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateDecryptor(Key, IV), CryptoStreamMode.Read);
```

<span data-ttu-id="bc872-114">В следующем примере показан весь процесс создания потока, расшифровки потока, чтения из потока и закрытия потока.</span><span class="sxs-lookup"><span data-stu-id="bc872-114">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="bc872-115">Создается объект <xref:System.Net.Sockets.TcpListener> , который инициализирует сетевой поток при подключении к прослушивающему объекту.</span><span class="sxs-lookup"><span data-stu-id="bc872-115">A <xref:System.Net.Sockets.TcpListener> object is created that initializes a network stream when a connection to the listening object is made.</span></span> <span data-ttu-id="bc872-116">Затем сетевой поток расшифровывается при помощи класса **CryptoStream** и класса **RijndaelManaged** .</span><span class="sxs-lookup"><span data-stu-id="bc872-116">The network stream is then decrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="bc872-117">В примере предполагается, что ключ и вектор инициализации были успешно перенесены или согласованы заранее.</span><span class="sxs-lookup"><span data-stu-id="bc872-117">This example assumes that the key and IV values have been either successfully transferred or previously agreed upon.</span></span> <span data-ttu-id="bc872-118">Он не показывает код, необходимый для шифрования и передачи этих значений.</span><span class="sxs-lookup"><span data-stu-id="bc872-118">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System.IO
Imports System.Net
Imports System.Net.Sockets
Imports System.Security.Cryptography
Imports System.Threading

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Initialize a TCPListener on port 11000
            'using the current IP address.
            Dim tcpListen As New TcpListener(IPAddress.Any, 11000)

            'Start the listener.
            tcpListen.Start()

            'Check for a connection every five seconds.
            While Not tcpListen.Pending()
                Console.WriteLine("Still listening. Will try in 5 seconds.")

                Thread.Sleep(5000)
            End While

            'Accept the client if one is found.
            Dim tcp As TcpClient = tcpListen.AcceptTcpClient()

            'Create a network stream from the connection.
            Dim netStream As NetworkStream = tcp.GetStream()

            'Create a new instance of the RijndaelManaged class
            'and decrypt the stream.
            Dim rmCrypto As New RijndaelManaged()

            'Create an instance of the CryptoStream class, pass it the NetworkStream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            netStream.Close()
            tcp.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The Listener Failed.")
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Net;
using System.Net.Sockets;
using System.Security.Cryptography;
using System.Threading;

class Class1
{
   static void Main(string[] args)
   {
      //The key and IV must be the same values that were used
      //to encrypt the stream.
      byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};
      try
      {
         //Initialize a TCPListener on port 11000
         //using the current IP address.
         TcpListener tcpListen = new TcpListener(IPAddress.Any, 11000);

         //Start the listener.
         tcpListen.Start();

         //Check for a connection every five seconds.
         while(!tcpListen.Pending())
         {
            Console.WriteLine("Still listening. Will try in 5 seconds.");
            Thread.Sleep(5000);
         }

         //Accept the client if one is found.
         TcpClient tcp = tcpListen.AcceptTcpClient();

         //Create a network stream from the connection.
         NetworkStream netStream = tcp.GetStream();

         //Create a new instance of the RijndaelManaged class
         // and decrypt the stream.
         RijndaelManaged rmCrypto = new RijndaelManaged();

         //Create a CryptoStream, pass it the NetworkStream, and decrypt
         //it with the Rijndael class using the key and IV.
         CryptoStream cryptStream = new CryptoStream(netStream,
            rmCrypto.CreateDecryptor(key, iv),
            CryptoStreamMode.Read);

         //Read the stream.
         StreamReader sReader = new StreamReader(cryptStream);

         //Display the message.
         Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

         //Close the streams.
         sReader.Close();
         netStream.Close();
         tcp.Close();
      }
      //Catch any exceptions.
      catch
      {
         Console.WriteLine("The Listener Failed.");
      }
   }
}
```

<span data-ttu-id="bc872-119">Для работы предыдущего примера к прослушивателю необходимо установить зашифрованное подключение.</span><span class="sxs-lookup"><span data-stu-id="bc872-119">For the previous sample to work, an encrypted connection must be made to the listener.</span></span> <span data-ttu-id="bc872-120">Это подключение должно использовать тот же ключ, вектор инициализации и алгоритм, который используется в прослушивателе.</span><span class="sxs-lookup"><span data-stu-id="bc872-120">The connection must use the same key, IV, and algorithm used in the listener.</span></span> <span data-ttu-id="bc872-121">Если такое подключение установлено, сообщение расшифровывается и выводится в консоли.</span><span class="sxs-lookup"><span data-stu-id="bc872-121">If such a connection is made, the message is decrypted and displayed to the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="bc872-122">Асимметричная расшифровка</span><span class="sxs-lookup"><span data-stu-id="bc872-122">Asymmetric Decryption</span></span>

<span data-ttu-id="bc872-123">Как правило, сторона (сторона А) создает как открытый, так и закрытый ключи и сохраняет их в памяти или в контейнере криптографических ключей.</span><span class="sxs-lookup"><span data-stu-id="bc872-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="bc872-124">Затем сторона А пересылает открытый ключ другой стороне (сторона Б).</span><span class="sxs-lookup"><span data-stu-id="bc872-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="bc872-125">С помощью открытого ключа сторона б шифрует данные и отправляет их обратно стороне A. После получения данных сторона A расшифровывает их с помощью закрытого ключа, который соответствует.</span><span class="sxs-lookup"><span data-stu-id="bc872-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="bc872-126">Расшифровка будет успешной только в том случае, если сторона А использует закрытый ключ, соответствующий открытому ключу, использованному стороной Б для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="bc872-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="bc872-127">Дополнительные сведения о хранении асимметричных ключей в безопасном контейнере криптографических ключей и последующем извлечении асимметричного ключа см. в разделе [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="bc872-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="bc872-128">Следующий пример иллюстрирует расшифровку двух массивов байтов, представляющих симметричный ключ и вектор инициализации.</span><span class="sxs-lookup"><span data-stu-id="bc872-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="bc872-129">Дополнительные сведения о способе извлечения асимметричного открытого ключа из объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider> в формате, допускающем простую отправку третьей стороне, см. в разделе [Encrypting Data](../../../docs/standard/security/encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="bc872-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object in a format that you can easily send to a third party, see [Encrypting Data](../../../docs/standard/security/encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSACryptoServiceProvider class.
Dim rsa As New RSACryptoServiceProvider()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, False)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, False)
```

```csharp
//Create a new instance of the RSACryptoServiceProvider class.
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, false);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , false);
```

## <a name="see-also"></a><span data-ttu-id="bc872-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc872-130">See also</span></span>

- [<span data-ttu-id="bc872-131">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="bc872-131">Generating Keys for Encryption and Decryption</span></span>](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="bc872-132">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="bc872-132">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)
- [<span data-ttu-id="bc872-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="bc872-133">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
