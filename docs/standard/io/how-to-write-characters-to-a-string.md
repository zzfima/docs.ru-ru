---
title: Практическое руководство. Запись символов в строку
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET Framework], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bea51eaf11bd9d73d5a68eb09795bd9f9f143f95
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44214476"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="ccb8e-102">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="ccb8e-102">How to: Write Characters to a String</span></span>
<span data-ttu-id="ccb8e-103">Следующий пример кода демонстрирует синхронную и асинхронную запись символов из массива символов в строку.</span><span class="sxs-lookup"><span data-stu-id="ccb8e-103">The following code examples write characters synchronously and asynchronously from a character array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccb8e-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ccb8e-104">Example</span></span>  
 <span data-ttu-id="ccb8e-105">Следующий пример синхронно записывает 5 символов из массива в строку.</span><span class="sxs-lookup"><span data-stu-id="ccb8e-105">The following example writes 5 characters synchronously from an array to a string.</span></span>  
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="ccb8e-106">Пример</span><span class="sxs-lookup"><span data-stu-id="ccb8e-106">Example</span></span>  
 <span data-ttu-id="ccb8e-107">Следующий пример асинхронным способом считывает все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняет их в массиве.</span><span class="sxs-lookup"><span data-stu-id="ccb8e-107">The next example reads all the characters asynchronously from a <xref:System.Windows.Controls.TextBox> control, and stores them in an array.</span></span> <span data-ttu-id="ccb8e-108">Затем он асинхронно записывает все буквы и символы-разделители в элемент управления <xref:System.Windows.Controls.TextBlock>, размещая их на отдельных строках с переводом строки.</span><span class="sxs-lookup"><span data-stu-id="ccb8e-108">It then asynchronously writes each letter or white space character on a separate line followed by a line break to a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ccb8e-109">См. также</span><span class="sxs-lookup"><span data-stu-id="ccb8e-109">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="ccb8e-110">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="ccb8e-110">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)  
- [<span data-ttu-id="ccb8e-111">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="ccb8e-111">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="ccb8e-112">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="ccb8e-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="ccb8e-113">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="ccb8e-113">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="ccb8e-114">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="ccb8e-114">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="ccb8e-115">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="ccb8e-115">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="ccb8e-116">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="ccb8e-116">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="ccb8e-117">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="ccb8e-117">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
