---
title: "Получение двоичных данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Получение двоичных данных
По умолчанию объект **DataReader** загружает входящие данные в виде строки, как только вся строка данных будет в наличии.  Однако для больших двоичных объектов \(BLOB\) требуется другая процедура, поскольку они могут содержать гигабайты данных, которые невозможно уместить в одной строке.  Метод **Command.ExecuteReader** имеет перегрузку, которая принимает аргумент <xref:System.Data.CommandBehavior>, чтобы изменять характер действий объекта **DataReader** по умолчанию.  Аргумент <xref:System.Data.CommandBehavior> можно передать методу **ExecuteReader**, чтобы изменить характер действий объекта **DataReader** по умолчанию, чтобы он загружал не строки данных, а последовательно сами данные по мере их поступления.  Это идеально подходит для загрузки больших двоичных объектов или других больших структур данных.  Отметим, что этот характер действий может зависеть от источника данных.  Например, при возвращении большого двоичного объекта из Microsoft Access он загружается в память целиком, а не последовательно по мере поступления.  
  
 При указании объекту **DataReader** использовать метод **SequentialAccess** важно отметить последовательность, в которой должны открываться возвращенные поля.  При характере действий объекта **DataReader** по умолчанию, когда загружается вся строка целиком, как только она есть в наличии, пока не будет считана следующая строка, доступ к возвращенным полям можно получить в любом порядке.  Однако при использовании метода **SequentialAccess** открывать поля, возвращенные объектом **DataReader**, необходимо по порядку.  Например, если запрос возвращает три столбца и третий из них \- это большой двоичный объект, необходимо возвратить значение первого и второго поля перед тем, как открыть данные большого двоичного объекта в третьем поле.  Если открыть третье поле сначала, то значения первого и второго полей будут недоступны.  Произойдет это потому, что метод **SequentialAccess** внес изменение в объект **DataReader**, согласно которому данные должны возвращаться последовательно. Поэтому, если объект **DataReader** считал последующие данные раньше предыдущих, предыдущие данные будут недоступны.  
  
 При доступе к данным в поле большого двоичного объекта используйте типизированные методы доступа **GetBytes** или **GetChars** объекта **DataReader**, которые заполняют массив данными.  Кроме того, для символьных данных можно воспользоваться методом **GetString**.  Однако для сохранения ресурсов системы лучше не загружать значение большого двоичного объекта в одну большую строковую переменную.  Вместо этого можно указать определенный размер буфера данных, которые должны быть возвращены, а также начальное положение для первого байта или символа, читаемого из возвращенных данных.  Методы **GetBytes** и **GetChars** возвращают значение `long`, которое представляет число возвращенных байт или символов.  Если методу **GetBytes** или **GetChars** передать пустой массив, то возвращенное длинное значение будет общим числом байт или символов в большом двоичном объекте.  При необходимости можно в массиве указать индекс в качестве начальной позиции для читаемых данных.  
  
## Пример  
 В следующем примере из образца базы данных **pubs** в Microsoft SQL Server возвращаются идентификатор и эмблема издателя.  Идентификатор издателя \- символьное поле `pub_id`, а эмблема \- изображение, которое является большим двоичным объектом.  Так как поле **logo** является битовой картой, двоичные данные в этом примере возвращаются при помощи метода **GetBytes**.  Обратите внимание, что в текущей строке данных идентификатор издателя читается до эмблемы, поскольку доступ к полям должен осуществляться последовательно.  
  
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
  writer.Write(outByte, 0, (int)retval - 1);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## См. также  
 [Working with DataReaders](http://msdn.microsoft.com/ru-ru/126a966a-d08d-4d22-a19f-f432908b2b54)   
 [Двоичные данные и данные большого размера SQL Server](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)