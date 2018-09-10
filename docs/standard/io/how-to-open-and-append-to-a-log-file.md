---
title: Практическое руководство. Открытие файла журнала и добавление в него данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 35a7d481cf82818054a852f7c2e142f615022fcb
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44271719"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="9d3d9-102">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="9d3d9-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="9d3d9-103"><xref:System.IO.StreamWriter> и <xref:System.IO.StreamReader> записывают данные в потоки и считывают данные из потоков.</span><span class="sxs-lookup"><span data-stu-id="9d3d9-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="9d3d9-104">Следующий пример кода открывает файл `log.txt` для получения входных данных или создает файл с таким именем, если он не существует, а затем добавляет сведения в конец файла.</span><span class="sxs-lookup"><span data-stu-id="9d3d9-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="9d3d9-105">После этого он выводит содержимое файла для отображения в стандартный поток вывода.</span><span class="sxs-lookup"><span data-stu-id="9d3d9-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="9d3d9-106">Вместо использованного здесь подхода вы можете сохранить данные в одной строке или в массиве строк и выполнить те же функции с помощью метода <xref:System.IO.File.WriteAllText%2A> или <xref:System.IO.File.WriteAllLines%2A>.</span><span class="sxs-lookup"><span data-stu-id="9d3d9-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d3d9-107">Пользователи Visual Basic могут использовать методы и свойства, предоставляемые классом <xref:Microsoft.VisualBasic.Logging.Log> или <xref:Microsoft.VisualBasic.FileIO.FileSystem>, для создания файлов журнала и записи данных в них.</span><span class="sxs-lookup"><span data-stu-id="9d3d9-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d3d9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9d3d9-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9d3d9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9d3d9-109">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="9d3d9-110">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="9d3d9-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="9d3d9-111">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="9d3d9-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="9d3d9-112">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="9d3d9-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="9d3d9-113">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="9d3d9-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="9d3d9-114">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="9d3d9-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="9d3d9-115">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="9d3d9-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="9d3d9-116">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="9d3d9-116">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
