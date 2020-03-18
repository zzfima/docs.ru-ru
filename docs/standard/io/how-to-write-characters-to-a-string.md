---
title: Практическое руководство. Запись символов в строку
ms.date: 01/21/2019
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
ms.openlocfilehash: ecbfa2de2c21ff79df269f74eeddfa0738e7e25c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160288"
---
# <a name="how-to-write-characters-to-a-string"></a><span data-ttu-id="935a7-102">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="935a7-102">How to: Write characters to a string</span></span>
<span data-ttu-id="935a7-103">Следующий пример кода демонстрирует синхронную или асинхронную запись символов из массива символов в строку.</span><span class="sxs-lookup"><span data-stu-id="935a7-103">The following code examples write characters synchronously or asynchronously from a character array into a string.</span></span>  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a><span data-ttu-id="935a7-104">Пример. Синхронная запись символов в консольном приложении</span><span class="sxs-lookup"><span data-stu-id="935a7-104">Example: Write characters synchronously in a console app</span></span>  
 <span data-ttu-id="935a7-105">В следующем примере используется <xref:System.IO.StringWriter> для синхронной записи пяти символов в объект <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="935a7-105">The following example uses a <xref:System.IO.StringWriter> to write five characters synchronously to a <xref:System.Text.StringBuilder> object.</span></span>
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a><span data-ttu-id="935a7-106">Пример. Запись символов в асинхронном режиме в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="935a7-106">Example: Write characters asynchronously in a WPF app</span></span>
 <span data-ttu-id="935a7-107">Ниже приведен пример кода за приложением WPF.</span><span class="sxs-lookup"><span data-stu-id="935a7-107">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="935a7-108">При загрузке окна пример асинхронным способом считывает все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняет их в массиве.</span><span class="sxs-lookup"><span data-stu-id="935a7-108">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="935a7-109">Затем он асинхронно записывает все буквы и пробелы в элемент управления <xref:System.Windows.Controls.TextBlock>, размещая их на отдельных строках.</span><span class="sxs-lookup"><span data-stu-id="935a7-109">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="935a7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="935a7-110">See also</span></span>

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [<span data-ttu-id="935a7-111">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="935a7-111">File and stream I/O</span></span>](../../../docs/standard/io/index.md)  
- [<span data-ttu-id="935a7-112">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="935a7-112">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="935a7-113">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="935a7-113">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="935a7-114">Практическое руководство. Считывание данных из нового файла и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="935a7-114">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="935a7-115">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="935a7-115">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="935a7-116">Практическое руководство. Чтение текста из файла</span><span class="sxs-lookup"><span data-stu-id="935a7-116">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="935a7-117">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="935a7-117">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="935a7-118">Практическое руководство. Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="935a7-118">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)
