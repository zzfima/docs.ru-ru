---
title: Как выполнить  Считывание символов из строки
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reading characters from strings
- data streams, reading characters from string
- I/O [.NET Framework], reading characters from strings
- reading data, strings
- streams, reading characters from string
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01d5fb2e4f785a4a510715b58e95d310a6ffa4e2
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675352"
---
# <a name="how-to-read-characters-from-a-string"></a><span data-ttu-id="c836c-102">Как выполнить  Считывание символов из строки</span><span class="sxs-lookup"><span data-stu-id="c836c-102">How to: Read characters from a string</span></span>
<span data-ttu-id="c836c-103">Следующий пример кода демонстрирует синхронное и асинхронное чтение символов из строки.</span><span class="sxs-lookup"><span data-stu-id="c836c-103">The following code examples show how to read characters synchronously or asynchronously from a string.</span></span>  
  
## <a name="example-read-characters-synchronously"></a><span data-ttu-id="c836c-104">Пример Синхронное чтение символов</span><span class="sxs-lookup"><span data-stu-id="c836c-104">Example: Read characters synchronously</span></span> 
 <span data-ttu-id="c836c-105">Этот пример синхронным образом считывает 13 символов из строки, сохраняет их в массиве и отображает.</span><span class="sxs-lookup"><span data-stu-id="c836c-105">This example reads 13 characters synchronously from a string, stores them in an array, and displays them.</span></span> <span data-ttu-id="c836c-106">Затем он считывает остальные символы строки, сохраняет их в массив, начиная с шестого элемента, и отображает содержимое массива.</span><span class="sxs-lookup"><span data-stu-id="c836c-106">The example then reads the rest of the characters in the string, stores them in the array starting at the sixth element, and displays the contents of the array.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## <a name="example-read-characters-asynchronously"></a><span data-ttu-id="c836c-107">Пример Асинхронное чтение символов</span><span class="sxs-lookup"><span data-stu-id="c836c-107">Example: Read characters asynchronously</span></span>  
 <span data-ttu-id="c836c-108">Ниже приведен пример кода за приложением WPF.</span><span class="sxs-lookup"><span data-stu-id="c836c-108">The next example is the code behind a WPF app.</span></span> <span data-ttu-id="c836c-109">При загрузке окна пример асинхронным способом считывает все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняет их в массиве.</span><span class="sxs-lookup"><span data-stu-id="c836c-109">On window load, the example asynchronously reads all characters from a <xref:System.Windows.Controls.TextBox> control and stores them in an array.</span></span> <span data-ttu-id="c836c-110">Затем он асинхронно записывает все буквы и пробелы в элемент управления <xref:System.Windows.Controls.TextBlock>, размещая их на отдельных строках.</span><span class="sxs-lookup"><span data-stu-id="c836c-110">It then asynchronously writes each letter or white-space character to a separate line of a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c836c-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c836c-111">See also</span></span>

- <xref:System.IO.StringReader>  
- <xref:System.IO.StringReader.Read%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="c836c-112">Асинхронный файловый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="c836c-112">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
- [<span data-ttu-id="c836c-113">Практическое руководство. Создание списка каталогов</span><span class="sxs-lookup"><span data-stu-id="c836c-113">How to: Create a directory listing</span></span>](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
- [<span data-ttu-id="c836c-114">Практическое руководство. Считывание данных из нового файла и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="c836c-114">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="c836c-115">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="c836c-115">How to: Open and append to a log file</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="c836c-116">Практическое руководство. Чтение текста из файла</span><span class="sxs-lookup"><span data-stu-id="c836c-116">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="c836c-117">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="c836c-117">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="c836c-118">Практическое руководство. Запись символов в строку</span><span class="sxs-lookup"><span data-stu-id="c836c-118">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="c836c-119">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="c836c-119">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
