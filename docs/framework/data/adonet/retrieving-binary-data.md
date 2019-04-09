---
title: Извлечение двоичных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 068b84e8704b54e6aea148ec5fc5bf9f0c4cb958
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085978"
---
# <a name="retrieving-binary-data"></a>Извлечение двоичных данных
По умолчанию **DataReader** загружает входящие данные как строка, как только вся строка данных доступен. Однако для больших двоичных объектов (BLOB) требуется другая процедура, поскольку они могут содержать гигабайты данных, которые невозможно уместить в одной строке. **Command.ExecuteReader** метод имеет перегрузку, которая будет принимать <xref:System.Data.CommandBehavior> аргумент для изменения поведения по умолчанию **DataReader**. Вы можете передать <xref:System.Data.CommandBehavior.SequentialAccess> для **ExecuteReader** метод для изменения поведения по умолчанию **DataReader** таким образом, чтобы вместо загрузки строк данных, он будет загружать данные последовательно мере их получения. Это идеально подходит для загрузки больших двоичных объектов или других больших структур данных. Отметим, что этот характер действий может зависеть от источника данных. Например, при возвращении большого двоичного объекта из Microsoft Access он загружается в память целиком, а не последовательно по мере поступления.  
  
 При задании **DataReader** использовать **SequentialAccess**, важно отметить последовательность, в которой осуществляется доступ к полях, возвращаемых. По умолчанию **DataReader**, который загружается вся строка целиком, как только она становится доступной, позволяет получить доступ к полях, возвращаемых в любом порядке, пока не будет считана следующая строка. При использовании **SequentialAccess** тем не менее, вы должны получить доступ к полям, возвращенным **DataReader** в порядке. Например, если запрос возвращает три столбца и третий из них - это большой двоичный объект, необходимо возвратить значение первого и второго поля перед тем, как открыть данные большого двоичного объекта в третьем поле. Если открыть третье поле сначала, то значения первого и второго полей будут недоступны. Это обусловлено **SequentialAccess** изменил **DataReader** для возврата данных в последовательности, а данные будут недоступны **DataReader** чтения после его.  
  
 При доступе к данным в поле BLOB-ОБЪЕКТОВ, используйте **GetBytes** или **GetChars** типизированные методы доступа к **DataReader**, которые заполняют массив данными. Можно также использовать **GetString** для символьных данных, тем не менее. Однако для сохранения ресурсов системы лучше не загружать значение большого двоичного объекта в одну большую строковую переменную. Вместо этого можно указать определенный размер буфера данных, которые должны быть возвращены, а также начальное положение для первого байта или символа, читаемого из возвращенных данных. **GetBytes** и **GetChars** вернет `long` значение, которое представляет число возвращенных байт или символов. Если передать массив значений null для **GetBytes** или **GetChars**, то возвращенное длинное значение будет иметь общее число байт или символов в большой двоичный объект. При необходимости можно в массиве указать индекс в качестве начальной позиции для читаемых данных.  
  
## <a name="example"></a>Пример  
 В следующем примере возвращается идентификатор и эмблема издателя из **pubs** образца базы данных в Microsoft SQL Server. Идентификатор издателя - символьное поле `pub_id`, а эмблема - изображение, которое является большим двоичным объектом. Так как **логотип** является битовая карта, в примере возвращается двоичных данных, используя **GetBytes**. Обратите внимание, что в текущей строке данных идентификатор издателя читается до эмблемы, поскольку доступ к полям должен осуществляться последовательно.  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a>См. также

- [Двоичные данные и данные большого объема SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
