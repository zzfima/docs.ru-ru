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
# <a name="retrieving-binary-data"></a><span data-ttu-id="f5d1f-102">Получение двоичных данных</span><span class="sxs-lookup"><span data-stu-id="f5d1f-102">Retrieving Binary Data</span></span>
<span data-ttu-id="f5d1f-103">По умолчанию **DataReader** загружает входящие данные в виде строки, как только имеется целый ряд данных.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="f5d1f-104">Однако для больших двоичных объектов (BLOB) требуется другая процедура, поскольку они могут содержать гигабайты данных, которые невозможно уместить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="f5d1f-105">Метод **Command.ExecuteReader** имеет перегрузку, <xref:System.Data.CommandBehavior> которая потребует аргумента для изменения поведения **DataReader**по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="f5d1f-106">Вы можете <xref:System.Data.CommandBehavior.SequentialAccess> перейти к методу **ВыполненияReader,** чтобы изменить поведение **DataReader** по умолчанию, чтобы вместо загрузки строк данных, он будет загружать данные последовательно, как он получил.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="f5d1f-107">Это идеально подходит для загрузки больших двоичных объектов или других больших структур данных.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="f5d1f-108">Отметим, что этот характер действий может зависеть от источника данных.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="f5d1f-109">Например, при возвращении большого двоичного объекта из Microsoft Access он загружается в память целиком, а не последовательно по мере поступления.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="f5d1f-110">При настройке **DataReader** для использования **SequentialAccess**важно отметить последовательность, в которой вы получаете доступ к возвращенным полям.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="f5d1f-111">Поведение **DataReader**по умолчанию, которое загружает всю строку, как только она доступна, позволяет получить доступ к полям, возвращенным в любом порядке, до следующего строки.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="f5d1f-112">При использовании **SequentialAccess** однако, вы должны получить доступ к полям, возвращенным **DataReader** в порядке.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="f5d1f-113">Например, если запрос возвращает три столбца и третий из них - это большой двоичный объект, необходимо возвратить значение первого и второго поля перед тем, как открыть данные большого двоичного объекта в третьем поле.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="f5d1f-114">Если открыть третье поле сначала, то значения первого и второго полей будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="f5d1f-115">Это связано с тем, что **SequentialAccess** изменил **DataReader,** чтобы вернуть данные в последовательности, и данные не доступны после того, как **DataReader** прочитал его.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="f5d1f-116">При доступе к данным в поле BLOB используйте **GetBytes** или **GetChars,** набранные аксессуарами **DataReader,** которые заполняют массив данными.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="f5d1f-117">Вы также можете использовать **GetString** для данных о персонажах; Однако.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="f5d1f-118">Однако для сохранения ресурсов системы лучше не загружать значение большого двоичного объекта в одну большую строковую переменную.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="f5d1f-119">Вместо этого можно указать определенный размер буфера данных, которые должны быть возвращены, а также начальное положение для первого байта или символа, читаемого из возвращенных данных.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="f5d1f-120">**GetBytes** и **GetChars** `long` вернут значение, которое представляет количество возвращенных байтов или возвращенных символов.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="f5d1f-121">Если вы передаете нулевую массив **GetBytes** или **GetChars,** возврат исчисляемый длинным значением будет общим числом байтов или символов в BLOB.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="f5d1f-122">При необходимости можно в массиве указать индекс в качестве начальной позиции для читаемых данных.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5d1f-123">Пример</span><span class="sxs-lookup"><span data-stu-id="f5d1f-123">Example</span></span>  
 <span data-ttu-id="f5d1f-124">Следующий пример возвращает идентификатор издателя и логотип из базы данных **образцов пабов** в Microsoft S'L Server.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="f5d1f-125">Идентификатор издателя - символьное поле `pub_id`, а эмблема - изображение, которое является большим двоичным объектом.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="f5d1f-126">Поскольку поле **логотипа** является битной картой, пример возвращает двоичные данные с помощью **GetBytes.**</span><span class="sxs-lookup"><span data-stu-id="f5d1f-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="f5d1f-127">Обратите внимание, что в текущей строке данных идентификатор издателя читается до эмблемы, поскольку доступ к полям должен осуществляться последовательно.</span><span class="sxs-lookup"><span data-stu-id="f5d1f-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5d1f-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5d1f-128">See also</span></span>

- [<span data-ttu-id="f5d1f-129">Двоичные и высокоценные данные сервера S'L</span><span class="sxs-lookup"><span data-stu-id="f5d1f-129">SQL Server Binary and Large-Value Data</span></span>](./sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="f5d1f-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f5d1f-130">ADO.NET Overview</span></span>](ado-net-overview.md)
