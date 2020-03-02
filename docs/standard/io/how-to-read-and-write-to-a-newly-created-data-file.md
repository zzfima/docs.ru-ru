---
title: Руководство. считывание данных из нового файла и запись в этот файл
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 3772aeeb25d1251a13fde2a0e51a913e5e39eabc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155754"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="0e731-102">Руководство. считывание данных из нового файла и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="0e731-102">How to: Read and write to a newly created data file</span></span>
<span data-ttu-id="0e731-103">Классы <xref:System.IO.BinaryWriter?displayProperty=nameWithType> и <xref:System.IO.BinaryReader?displayProperty=nameWithType> используются для записи и чтения данных вместо строк символов.</span><span class="sxs-lookup"><span data-stu-id="0e731-103">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="0e731-104">Следующий пример показывает, как создать пустой файловый поток, записать в него данные, а затем считать их.</span><span class="sxs-lookup"><span data-stu-id="0e731-104">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span>

<span data-ttu-id="0e731-105">В этом примере создается файл данных *Test.data* в текущем каталоге, создаются связанные с ним объекты <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader>, а затем применяется объект <xref:System.IO.BinaryWriter> для записи целых чисел от 0 до 10 в *Test.data*. По завершении этих действий указатель файла остается в конце файла.</span><span class="sxs-lookup"><span data-stu-id="0e731-105">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data*, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="0e731-106">Затем объект <xref:System.IO.BinaryReader> возвращает указатель файла в начало и считывает его содержимое.</span><span class="sxs-lookup"><span data-stu-id="0e731-106">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e731-107">Если *Test.data* уже существует в текущем каталоге, создается исключение <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="0e731-107">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="0e731-108">Используйте параметр файлового режима <xref:System.IO.FileMode.Create?displayProperty=nameWithType> вместо <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>, чтобы всегда создавать новый файл без появления исключения.</span><span class="sxs-lookup"><span data-stu-id="0e731-108">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e731-109">Пример</span><span class="sxs-lookup"><span data-stu-id="0e731-109">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="0e731-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e731-110">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="0e731-111">Руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="0e731-111">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="0e731-112">Руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="0e731-112">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="0e731-113">Руководство. Чтение текста из файла</span><span class="sxs-lookup"><span data-stu-id="0e731-113">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="0e731-114">Руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="0e731-114">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="0e731-115">Руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="0e731-115">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="0e731-116">Руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="0e731-116">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="0e731-117">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="0e731-117">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
