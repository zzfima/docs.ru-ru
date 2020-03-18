---
title: Практическое руководство. Запись текста в файл
ms.date: 01/04/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- writing text to files
- I/O [.NET Framework], writing text to files
- streams, writing text to files
- data streams, writing text to files
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
ms.openlocfilehash: ba1c1815f0e49c02d1f0ee3c48ba01b7c2f5e727
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160252"
---
# <a name="how-to-write-text-to-a-file"></a>Практическое руководство. Запись текста в файл
В этом разделе показаны различные способы записи текста в файл для приложения .NET.

Для записи текста в файл обычно используются следующие классы и методы.  
  
- <xref:System.IO.StreamWriter> содержит методы для синхронной (<xref:System.IO.StreamWriter.Write%2A> или <xref:System.IO.TextWriter.WriteLine%2A>) или асинхронной (<xref:System.IO.StreamWriter.WriteAsync%2A> и <xref:System.IO.StreamWriter.WriteLineAsync%2A>) записи в файл.  
  
- <xref:System.IO.File> предоставляет статические методы для записи текста в файл, такие как <xref:System.IO.File.WriteAllLines%2A> и <xref:System.IO.File.WriteAllText%2A>, или для добавления текста в файл (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> или <xref:System.IO.File.AppendText%2A>).  
  
- <xref:System.IO.Path> предназначен для использования со строками, содержащими сведения о пути к файлу или каталогу. Он содержит метод <xref:System.IO.Path.Combine%2A>; в .NET Core 2.1 и более поздних версиях также есть методы <xref:System.IO.Path.Join%2A> и <xref:System.IO.Path.TryJoin%2A>, которые позволяют объединять строки для создания пути к файлу или каталогу.

> [!NOTE]
> Нижеприведенные примеры демонстрируют минимальный объем необходимого кода. Реальное приложение обычно обеспечивает более надежную проверку ошибок и обработку исключений.  
  
## <a name="example-synchronously-write-text-with-streamwriter"></a>Пример. Синхронная запись текста с помощью StreamWriter

В следующем примере показано, как синхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> по одной строке за раз. Поскольку объект <xref:System.IO.StreamWriter> объявляется и создается в инструкции `using`, вызывается метод <xref:System.IO.StreamWriter.Dispose%2A>, который автоматически выполняет очистку и закрывает поток.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/write.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/write.vb)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="example-synchronously-append-text-with-streamwriter"></a>Пример. Синхронное добавление текста с помощью StreamWriter

В следующем примере показано, как использовать класс <xref:System.IO.StreamWriter>, чтобы синхронно добавить текст в текстовый файл, созданный в первом примере.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/append.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/append.vb)]  

## <a name="example-asynchronously-write-text-with-streamwriter"></a>Пример. Асинхронная запись текста с помощью StreamWriter

В следующем примере показано, как асинхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> . Вызов метода <xref:System.IO.StreamWriter.WriteAsync%2A> должен находиться в методе `async`. Для примера на C# требуется C# 7.1 или более поздней версии, где добавлена поддержка модификатора `async` для точки входа программы.

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/async.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/async.vb)]  

## <a name="example-write-and-append-text-with-the-file-class"></a>Пример. Запись и добавление текста с помощью класса File

В следующем примере показано, как записать текст в новый файл и добавить новые строки текста в тот же файл с помощью класса <xref:System.IO.File> . Методы <xref:System.IO.File.WriteAllText%2A> и <xref:System.IO.File.AppendAllLines%2A> открывают и закрывают файл автоматически. Если предоставленный в методе <xref:System.IO.File.WriteAllText%2A> путь уже существует, файл будет перезаписан.  

[!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/file.cs)]
[!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/file.vb)]  

## <a name="see-also"></a>См. также

- <xref:System.IO.StreamWriter>
- <xref:System.IO.Path>
- <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>
- [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)
- [Практическое руководство. Считывание данных из нового файла и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)
- [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)
- [Практическое руководство. Чтение текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)
- [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)
