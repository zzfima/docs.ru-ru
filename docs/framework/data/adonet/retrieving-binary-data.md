---
title: Извлечение двоичных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 9acda6631e17031a81ba06d9530739a586fac7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794430"
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="b10a0-102">Извлечение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="b10a0-102">Retrieving Binary Data</span></span>
<span data-ttu-id="b10a0-103">По умолчанию **DataReader** загружает входящие данные в виде строки, как только будет доступна вся строка данных.</span><span class="sxs-lookup"><span data-stu-id="b10a0-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="b10a0-104">Однако для больших двоичных объектов (BLOB) требуется другая процедура, поскольку они могут содержать гигабайты данных, которые невозможно уместить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="b10a0-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="b10a0-105">Метод **Command. ExecuteReader** имеет перегрузку, которая принимает <xref:System.Data.CommandBehavior> аргумент, чтобы изменить поведение **DataReader**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b10a0-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="b10a0-106">Можно передать <xref:System.Data.CommandBehavior.SequentialAccess> методу **ExecuteReader** , чтобы изменить поведение **DataReader** по умолчанию, так что вместо загрузки строк данных он будет загружать данные последовательно по мере получения.</span><span class="sxs-lookup"><span data-stu-id="b10a0-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="b10a0-107">Это идеально подходит для загрузки больших двоичных объектов или других больших структур данных.</span><span class="sxs-lookup"><span data-stu-id="b10a0-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="b10a0-108">Отметим, что этот характер действий может зависеть от источника данных.</span><span class="sxs-lookup"><span data-stu-id="b10a0-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="b10a0-109">Например, при возвращении большого двоичного объекта из Microsoft Access он загружается в память целиком, а не последовательно по мере поступления.</span><span class="sxs-lookup"><span data-stu-id="b10a0-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="b10a0-110">При настройке **DataReader** для использования **SequentialAccess**важно отметить последовательность, в которой осуществляется доступ к возвращенным полям.</span><span class="sxs-lookup"><span data-stu-id="b10a0-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="b10a0-111">Поведение объекта **DataReader**по умолчанию, которое загружает всю строку сразу после ее доступности, позволяет получить доступ к полям, возвращаемым в любом порядке, пока не будет считано Следующая строка.</span><span class="sxs-lookup"><span data-stu-id="b10a0-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="b10a0-112">Однако при использовании **SequentialAccess** необходимо получить доступ к полям, возвращаемым объектом **DataReader** по порядку.</span><span class="sxs-lookup"><span data-stu-id="b10a0-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="b10a0-113">Например, если запрос возвращает три столбца и третий из них - это большой двоичный объект, необходимо возвратить значение первого и второго поля перед тем, как открыть данные большого двоичного объекта в третьем поле.</span><span class="sxs-lookup"><span data-stu-id="b10a0-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="b10a0-114">Если открыть третье поле сначала, то значения первого и второго полей будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="b10a0-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="b10a0-115">Это обусловлено тем, что **SequentialAccess** изменил объект **DataReader** для возвращения данных последовательно, и данные недоступны после того, как **DataReader** прочитал его.</span><span class="sxs-lookup"><span data-stu-id="b10a0-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="b10a0-116">При доступе к данным в поле BLOB-объекта используйте типизированные методы доступа **GetBytes** или **GetChars** для **DataReader**, которые заполняют массив данными.</span><span class="sxs-lookup"><span data-stu-id="b10a0-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="b10a0-117">**GetString** можно также использовать для символьных данных. Несмотря.</span><span class="sxs-lookup"><span data-stu-id="b10a0-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="b10a0-118">Однако для сохранения ресурсов системы лучше не загружать значение большого двоичного объекта в одну большую строковую переменную.</span><span class="sxs-lookup"><span data-stu-id="b10a0-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="b10a0-119">Вместо этого можно указать определенный размер буфера данных, которые должны быть возвращены, а также начальное положение для первого байта или символа, читаемого из возвращенных данных.</span><span class="sxs-lookup"><span data-stu-id="b10a0-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="b10a0-120">**GetBytes** и **GetChars** `long` будут возвращать значение, представляющее число возвращаемых байтов или символов.</span><span class="sxs-lookup"><span data-stu-id="b10a0-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="b10a0-121">Если передать массив null в **GetBytes** или **GetChars**, возвращается значение Long, равное общему числу байтов или символов в большом двоичном объекте.</span><span class="sxs-lookup"><span data-stu-id="b10a0-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="b10a0-122">При необходимости можно в массиве указать индекс в качестве начальной позиции для читаемых данных.</span><span class="sxs-lookup"><span data-stu-id="b10a0-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b10a0-123">Пример</span><span class="sxs-lookup"><span data-stu-id="b10a0-123">Example</span></span>  
 <span data-ttu-id="b10a0-124">В следующем примере возвращается идентификатор издателя и логотип из образца базы данных **pubs** в Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b10a0-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="b10a0-125">Идентификатор издателя - символьное поле `pub_id`, а эмблема - изображение, которое является большим двоичным объектом.</span><span class="sxs-lookup"><span data-stu-id="b10a0-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="b10a0-126">Поскольку поле **Logo** является точечным рисунком, пример возвращает двоичные данные с помощью **GetBytes**.</span><span class="sxs-lookup"><span data-stu-id="b10a0-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="b10a0-127">Обратите внимание, что в текущей строке данных идентификатор издателя читается до эмблемы, поскольку доступ к полям должен осуществляться последовательно.</span><span class="sxs-lookup"><span data-stu-id="b10a0-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b10a0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b10a0-128">See also</span></span>

- [<span data-ttu-id="b10a0-129">Двоичные данные и данные большого объема SQL Server</span><span class="sxs-lookup"><span data-stu-id="b10a0-129">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="b10a0-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b10a0-130">ADO.NET Overview</span></span>](ado-net-overview.md)
