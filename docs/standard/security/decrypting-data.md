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
# <a name="decrypting-data"></a>Расшифровка данных

Расшифровка представляет собой операцию, обратную операции шифрования. Для шифрования с секретным ключом необходимо знать как ключ, так и вектор инициализации, которые использовались при шифровании данных. Для шифрования с открытым ключом необходимо знать либо открытый ключ (если данные были зашифрованы при помощи закрытого ключа), либо закрытый ключ (если данные были зашифрованы при помощи открытого ключа).

## <a name="symmetric-decryption"></a>Симметричная расшифровка

Расшифровка данных, зашифрованных при помощи симметричных алгоритмов, похожа на процесс, используемый для шифрования данных при помощи симметричных алгоритмов. Класс <xref:System.Security.Cryptography.CryptoStream> используется с классами симметричного шифрования, предоставляемыми платформой .NET Framework, для расшифровки данных, считанных из любого управляемого объекта потока.

В следующем примере показано, как создать новый экземпляр класса <xref:System.Security.Cryptography.RijndaelManaged> и использовать его для расшифровки объекта <xref:System.Security.Cryptography.CryptoStream> . Этот пример сначала создает новый экземпляр класса **RijndaelManaged** . Затем он создает объект **CryptoStream** и инициализирует его значением управляемого потока, вызвавшего `myStream`. Далее в метод **CreateDecryptor** из класса **RijndaelManaged** передается тот же ключ и вектор инициализации, которые использовались для шифрования, а затем метод передается в конструктор **CryptoStream** . Наконец, перечисление **CryptoStreamMode.Read** передается в конструктор **CryptoStream** , чтобы задать доступ на чтение для потока.

```vb
Dim rmCrypto As New RijndaelManaged()
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateDecryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Read)
```

```csharp
RijndaelManaged rmCrypto = new RijndaelManaged();
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateDecryptor(Key, IV), CryptoStreamMode.Read);
```

В следующем примере показан весь процесс создания потока, расшифровки потока, чтения из потока и закрытия потока. Создается объект <xref:System.Net.Sockets.TcpListener> , который инициализирует сетевой поток при подключении к прослушивающему объекту. Затем сетевой поток расшифровывается при помощи класса **CryptoStream** и класса **RijndaelManaged** . В примере предполагается, что ключ и вектор инициализации были успешно перенесены или согласованы заранее. Он не показывает код, необходимый для шифрования и передачи этих значений.

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

Для работы предыдущего примера к прослушивателю необходимо установить зашифрованное подключение. Это подключение должно использовать тот же ключ, вектор инициализации и алгоритм, который используется в прослушивателе. Если такое подключение установлено, сообщение расшифровывается и выводится в консоли.

## <a name="asymmetric-decryption"></a>Асимметричная расшифровка

Как правило, сторона (сторона А) создает как открытый, так и закрытый ключи и сохраняет их в памяти или в контейнере криптографических ключей. Затем сторона А пересылает открытый ключ другой стороне (сторона Б). С помощью открытого ключа сторона б шифрует данные и отправляет их обратно стороне A. После получения данных сторона A расшифровывает их с помощью закрытого ключа, который соответствует. Расшифровка будет успешной только в том случае, если сторона А использует закрытый ключ, соответствующий открытому ключу, использованному стороной Б для шифрования данных.

Дополнительные сведения о хранении асимметричных ключей в безопасном контейнере криптографических ключей и последующем извлечении асимметричного ключа см. в разделе [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).

Следующий пример иллюстрирует расшифровку двух массивов байтов, представляющих симметричный ключ и вектор инициализации. Дополнительные сведения о способе извлечения асимметричного открытого ключа из объекта <xref:System.Security.Cryptography.RSACryptoServiceProvider> в формате, допускающем простую отправку третьей стороне, см. в разделе [Encrypting Data](../../../docs/standard/security/encrypting-data.md).

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

## <a name="see-also"></a>См. также:

- [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)
- [Шифрование данных](../../../docs/standard/security/encrypting-data.md)
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
