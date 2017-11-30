---
title: "Практическое руководство. Открытие файла журнала и добавление в него данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="0519f-102">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="0519f-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="0519f-103"><xref:System.IO.StreamWriter>и <xref:System.IO.StreamReader> для записи и чтения знаков из потоков.</span><span class="sxs-lookup"><span data-stu-id="0519f-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="0519f-104">В следующем примере кода открывается `log.txt` входных данных в файле, или создает файл, если он еще не существует и добавляет сведения в конец файла.</span><span class="sxs-lookup"><span data-stu-id="0519f-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="0519f-105">Содержимое файла, затем записываются в стандартный поток вывода для отображения.</span><span class="sxs-lookup"><span data-stu-id="0519f-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="0519f-106">В качестве альтернативы, к примеру, данные могут храниться как одна строка или массив строк и <xref:System.IO.File.WriteAllText%2A> или <xref:System.IO.File.WriteAllLines%2A> метод может использоваться для той же функциональности.</span><span class="sxs-lookup"><span data-stu-id="0519f-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0519f-107">Пользователи Visual Basic, можно использовать методы и свойства, предоставляемые <xref:Microsoft.VisualBasic.Logging.Log> класса или <xref:Microsoft.VisualBasic.FileIO.FileSystem> класс для создания и записи в файлы журнала.</span><span class="sxs-lookup"><span data-stu-id="0519f-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0519f-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0519f-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0519f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0519f-109">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="0519f-110">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="0519f-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="0519f-111">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="0519f-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="0519f-112">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="0519f-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="0519f-113">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="0519f-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="0519f-114">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="0519f-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="0519f-115">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="0519f-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="0519f-116">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="0519f-116">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
