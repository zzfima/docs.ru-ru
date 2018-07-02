---
title: Практическое руководство. Считывание текста из файла
ms.date: 06/19/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b7c54e5e55770f3df44819cdf6d2d2c866f7e0fc
ms.sourcegitcommit: 640cee8fc5d256cdd80e5b80240469feac10499e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "36298166"
---
# <a name="how-to-read-text-from-a-file"></a>Практическое руководство. Считывание текста из файла
В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений. В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу. В следующих примерах предполагается, что файл с именем TestFile.txt находится в той же папке, что и приложение.  
  
 Эти примеры кода не относятся к разработке приложений для Microsoft Store, поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов. Пример чтения текста из файла в приложении Microsoft Store см. в разделе [Краткое руководство. Чтение и запись файлов](https://docs.microsoft.com/en-us/previous-versions/windows/apps/hh758325(v=win.10)). Примеры преобразования между потоками NET Framework и потоками среды выполнения Windows см. в разделе [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует синхронную операцию чтения в консольном приложении. В этом примере текстовый файл открывается с помощью средства чтения потока, содержимое копируется в строку, а строка выводится на консоль.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## <a name="example"></a>Пример  
 Следующий пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation (WPF).  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [Асинхронный файловый ввод-вывод](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [Практическое руководство. Создание списка каталогов](https://msdn.microsoft.com/library/4d2772b1-b991-4532-a8a6-6ef733277e69)  
 [Краткое руководство. Чтение и запись файлов](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)  
 [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
