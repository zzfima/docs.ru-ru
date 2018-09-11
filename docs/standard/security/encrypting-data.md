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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b583df2eb6098fa28dd8999a6796e5053d13cab4
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272414"
---
# <a name="encrypting-data"></a>Шифрование данных
Симметричное и асимметричное шифрования выполняются с использованием различных процессов. Симметричное шифрование выполняется в рамках потоков, поэтому его удобно применять для шифрования больших объемов данных. Асимметричное шифрование выполняется в рамках небольшого числа байтов, поэтому его удобно применять для шифрования только небольших объемов данных.  
  
## <a name="symmetric-encryption"></a>Симметричное шифрование  
 Управляемые классы симметричного шифрования используются со специальным классом потока <xref:System.Security.Cryptography.CryptoStream> , который шифрует данные, считанные в поток. Класс **CryptoStream** инициализируется при помощи управляемого класса потока, класса, реализующего интерфейс <xref:System.Security.Cryptography.ICryptoTransform> (созданный из класса, который реализует алгоритм шифрования), и перечисления <xref:System.Security.Cryptography.CryptoStreamMode> , описывающего разрешенный тип доступа для **CryptoStream**. Класс **CryptoStream** может быть инициализирован при помощи любого класса, производного от класса <xref:System.IO.Stream> , включая <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>и <xref:System.Net.Sockets.NetworkStream>. При помощи этих классов можно осуществлять симметричное шифрование для различных объектов потока.  
  
 В следующем примере показано, как создать новый экземпляр класса <xref:System.Security.Cryptography.RijndaelManaged> , который реализует алгоритм шифрования Rijndael, и использовать его для шифрования класса **CryptoStream** . В этом примере **CryptoStream** инициализируется при помощи объекта потока `MyStream` , который может быть любым типом управляемого потока. В метод **CreateEncryptor** из класса **RijndaelManaged** передается ключ и вектор инициализации, используемые для шифрования. В этом случае используется ключ и вектор инициализации по умолчанию, созданные из `RMCrypto` . Наконец, передается **CryptoStreamMode.Write** , указывая доступ на запись к потоку.  
  
```vb  
Dim RMCrypto As New RijndaelManaged()  
Dim CryptStream As New CryptoStream(MyStream, RMCrypto.CreateEncryptor(RMCrypto.Key, RMCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged RMCrypto = new RijndaelManaged();  
CryptoStream CryptStream = new CryptoStream(MyStream, RMCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 После выполнения этого кода все данные, записанные в объект **CryptoStream** , шифруются при помощи алгоритма Rijndael.  
  
 В следующем примере показан весь процесс создания потока, шифрования потока, чтения из потока и закрытия потока. Этот пример создает сетевой поток, который шифруется при помощи класса **CryptoStream** и класса **RijndaelManaged** . Сообщение записывается в зашифрованный поток при помощи класса <xref:System.IO.StreamWriter> .  
  
> [!NOTE]
>  Этот пример также можно использовать для записи в файл. Чтобы сделать это, удалите ссылку <xref:System.Net.Sockets.TcpClient> и замените <xref:System.Net.Sockets.NetworkStream> на <xref:System.IO.FileStream>.  
  
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
      Dim TCP As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.   
      Dim NetStream As NetworkStream = TCP.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim RMCrypto As New RijndaelManaged()  
  
            Dim Key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim IV As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt   
      'it with the Rijndael class.  
      Dim CryptStream As New CryptoStream(NetStream, RMCrypto.CreateEncryptor(Key, IV), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the   
      'network stream.  
      Dim SWriter As New StreamWriter(CryptStream)  
  
      'Write to the stream.  
      SWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      SWriter.Close()  
      CryptStream.Close()  
      NetStream.Close()  
      TCP.Close()  
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
         TcpClient TCP = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.   
         NetworkStream NetStream = TCP.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged RMCrypto = new RijndaelManaged();  
  
         byte[] Key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] IV = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt   
         //it with the Rijndael class.  
         CryptoStream CryptStream = new CryptoStream(NetStream,   
         RMCrypto.CreateEncryptor(Key, IV),     
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the   
         //network stream.  
         StreamWriter SWriter = new StreamWriter(CryptStream);  
  
         //Write to the stream.  
         SWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         SWriter.Close();  
         CryptStream.Close();  
         NetStream.Close();  
         TCP.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 В предыдущем примере для успешного выполнения должен присутствовать процесс, прослушивающий IP-адрес и номер порта, указанные в классе <xref:System.Net.Sockets.TcpClient> . Если прослушивающий процесс существует, код будет подключаться к нему, шифровать поток при помощи симметричного алгоритма Rijndael и записывать фразу "Hello World!" в этот поток. При успешном выполнении код выводит в консоли следующий текст:  
  
```  
The message was sent.  
```  
  
 Однако если указанный прослушивающий процесс отсутствует или возникает исключение, код отображает в консоли следующий текст:  
  
```  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a>Асимметричное шифрование  
 Асимметричные алгоритмы обычно используются для шифрования малых объемов данных, например для шифрования симметричного ключа и вектора инициализации. Как правило, сторона, осуществляющая асимметричное шифрование, использует открытый ключ, созданный другой стороной. Для этих целей платформа .NET Framework предоставляет класс <xref:System.Security.Cryptography.RSACryptoServiceProvider> .  
  
 В следующем примере сведения об открытом ключе используются для шифрования симметричного ключа и вектора инициализации. Инициализируются два массива байтов, представляющих открытый ключ третьей стороны. Объект <xref:System.Security.Cryptography.RSAParameters> инициализируется с этими значениями. Далее, **RSAParameters** (вместе с представляемым им открытым ключом) импортируется в **RSACryptoServiceProvider** с помощью <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> метод. Наконец, выполняется шифрование закрытого ключа и вектора инициализации, созданных классом <xref:System.Security.Cryptography.RijndaelManaged> . В этом примере требуется, чтобы в системе было установлено 128-битное шифрование.  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim PublicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim Exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim EncryptedSymmetricKey() As Byte  
        Dim EncryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim RSAKeyInfo As New RSAParameters()  
  
        'Set RSAKeyInfo to the public key values.   
        RSAKeyInfo.Modulus = PublicKey  
        RSAKeyInfo.Exponent = Exponent  
  
        'Import key parameters into RSA.  
        RSA.ImportParameters(RSAKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        EncryptedSymmetricKey = RSA.Encrypt(RM.Key, False)  
        EncryptedSymmetricIV = RSA.Encrypt(RM.IV, False)  
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
      byte[] PublicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] Exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] EncryptedSymmetricKey;  
      byte[] EncryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters RSAKeyInfo = new RSAParameters();  
  
      //Set RSAKeyInfo to the public key values.   
      RSAKeyInfo.Modulus = PublicKey;  
      RSAKeyInfo.Exponent = Exponent;  
  
      //Import key parameters into RSA.  
      RSA.ImportParameters(RSAKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged RM = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      EncryptedSymmetricKey = RSA.Encrypt(RM.Key, false);  
      EncryptedSymmetricIV = RSA.Encrypt(RM.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a>См. также

- [Создание ключей для шифрования и расшифровки](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)  
- [Расшифровка данных](../../../docs/standard/security/decrypting-data.md)  
- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
