---
title: Получение двоичных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: c914a9b0780e2e87e177502b0f9faff0e7c4b617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149054"
---
# <a name="retrieving-binary-data"></a>Получение двоичных данных
По умолчанию **DataReader** загружает входящие данные в виде строки, как только имеется целый ряд данных. Однако для больших двоичных объектов (BLOB) требуется другая процедура, поскольку они могут содержать гигабайты данных, которые невозможно уместить в одной строке. Метод **Command.ExecuteReader** имеет перегрузку, <xref:System.Data.CommandBehavior> которая потребует аргумента для изменения поведения **DataReader**по умолчанию. Вы можете <xref:System.Data.CommandBehavior.SequentialAccess> перейти к методу **ВыполненияReader,** чтобы изменить поведение **DataReader** по умолчанию, чтобы вместо загрузки строк данных, он будет загружать данные последовательно, как он получил. Это идеально подходит для загрузки больших двоичных объектов или других больших структур данных. Отметим, что этот характер действий может зависеть от источника данных. Например, при возвращении большого двоичного объекта из Microsoft Access он загружается в память целиком, а не последовательно по мере поступления.  
  
 При настройке **DataReader** для использования **SequentialAccess**важно отметить последовательность, в которой вы получаете доступ к возвращенным полям. Поведение **DataReader**по умолчанию, которое загружает всю строку, как только она доступна, позволяет получить доступ к полям, возвращенным в любом порядке, до следующего строки. При использовании **SequentialAccess** однако, вы должны получить доступ к полям, возвращенным **DataReader** в порядке. Например, если запрос возвращает три столбца и третий из них - это большой двоичный объект, необходимо возвратить значение первого и второго поля перед тем, как открыть данные большого двоичного объекта в третьем поле. Если открыть третье поле сначала, то значения первого и второго полей будут недоступны. Это связано с тем, что **SequentialAccess** изменил **DataReader,** чтобы вернуть данные в последовательности, и данные не доступны после того, как **DataReader** прочитал его.  
  
 При доступе к данным в поле BLOB используйте **GetBytes** или **GetChars,** набранные аксессуарами **DataReader,** которые заполняют массив данными. Вы также можете использовать **GetString** для данных о персонажах; Однако. Однако для сохранения ресурсов системы лучше не загружать значение большого двоичного объекта в одну большую строковую переменную. Вместо этого можно указать определенный размер буфера данных, которые должны быть возвращены, а также начальное положение для первого байта или символа, читаемого из возвращенных данных. **GetBytes** и **GetChars** `long` вернут значение, которое представляет количество возвращенных байтов или возвращенных символов. Если вы передаете нулевую массив **GetBytes** или **GetChars,** возврат исчисляемый длинным значением будет общим числом байтов или символов в BLOB. При необходимости можно в массиве указать индекс в качестве начальной позиции для читаемых данных.  
  
## <a name="example"></a>Пример  
 Следующий пример возвращает идентификатор издателя и логотип из базы данных **образцов пабов** в Microsoft S'L Server. Идентификатор издателя - символьное поле `pub_id`, а эмблема - изображение, которое является большим двоичным объектом. Поскольку поле **логотипа** является битной картой, пример возвращает двоичные данные с помощью **GetBytes.** Обратите внимание, что в текущей строке данных идентификатор издателя читается до эмблемы, поскольку доступ к полям должен осуществляться последовательно.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Двоичные и высокоценные данные сервера S'L](./sql/sql-server-binary-and-large-value-data.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
