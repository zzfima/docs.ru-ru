---
title: Практическое руководство. Считывание из нового файла данных и запись в этот файл
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b854495a32755b2cbbd0421b1a45458fd2b7863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="b8b4b-102">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="b8b4b-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="b8b4b-103">Классы <xref:System.IO.BinaryWriter> И <xref:System.IO.BinaryReader?displayProperty=nameWithType> используются для записи и чтения данных вместо строк символов.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="b8b4b-104">Следующий пример демонстрирует запись данных в новый пустой файловый поток с именем `Test.data` и чтение данных из него.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="b8b4b-105">Этот код создает файл данных в текущем каталоге, создает связанные с ним объекты <xref:System.IO.BinaryWriter> и <xref:System.IO.BinaryReader>, а затем применяет объект <xref:System.IO.BinaryWriter> для записи в `Test.data` целых чисел с 0 до 10. По завершении этих действий указатель файла остается в конце файла.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="b8b4b-106">Затем пример кода возвращает указатель файла в начало и через объект <xref:System.IO.BinaryReader> считывает его содержимое.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8b4b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="b8b4b-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="b8b4b-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="b8b4b-108">Robust Programming</span></span>  
 <span data-ttu-id="b8b4b-109">Если `Test.data` уже существует в текущем каталоге, создается исключение <xref:System.IO.IOException>.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="b8b4b-110">Используйте параметр <xref:System.IO.FileMode.Create?displayProperty=nameWithType> файлового режима при инициализации файлового потока, чтобы всегда создавать новый файл без появления исключения.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b4b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b8b4b-111">See Also</span></span>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [<span data-ttu-id="b8b4b-112">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="b8b4b-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="b8b4b-113">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="b8b4b-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="b8b4b-114">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="b8b4b-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="b8b4b-115">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="b8b4b-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="b8b4b-116">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="b8b4b-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="b8b4b-117">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="b8b4b-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="b8b4b-118">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="b8b4b-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
