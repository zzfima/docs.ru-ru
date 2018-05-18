---
title: Асинхронный файловый ввод-вывод
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, synchronous streams
- asynchronous I/O
- synchronous I/O
- streams, asynchronous streams
- I/O [.NET Framework], asynchronous I/O
- Stream class, synchronous I/O
- data streams, asynchronous streams
- Stream class, asynchronous I/O
- multiple I/O requests
- data streams, synchronous streams
ms.assetid: dbdd55e7-d6b9-4f9e-8abb-ab0edd4457f7
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 270ae5a8cfa7c69c7caa0896dfe23b84db48f659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="asynchronous-file-io"></a>Асинхронный файловый ввод-вывод
Асинхронные операции позволяют выполнять ресурсоемкие операции ввода-вывода без блокировки основного потока. Это соображение, связанное с производительностью, особенно важно в приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] и [!INCLUDE[desktop_appname](../../../includes/desktop-appname-md.md)] , где длительная потоковая операция может блокировать поток пользовательского интерфейса и создавать впечатление, что приложение не работает.  
  
 Начиная с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], для упрощения асинхронных операций типы ввода-вывода включают в себя асинхронные методы. Асинхронный метод содержит `Async` в своем имени, например <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>и <xref:System.IO.TextReader.ReadToEndAsync%2A>. Эти асинхронные методы реализуются на базе классов потоков, таких как <xref:System.IO.Stream>, <xref:System.IO.FileStream>и <xref:System.IO.MemoryStream>, а также классов, используемых для чтения или записи данных в потоках, таких как <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.  
  
 В платформе .NET Framework 4 и более ранних версий для реализации операций асинхронного ввода-вывода необходимо использовать такие методы, как <xref:System.IO.Stream.BeginRead%2A> и <xref:System.IO.Stream.EndRead%2A> . Эти методы по-прежнему доступны в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] для поддержки устаревшего кода. Однако асинхронные методы позволяют реализовать операции асинхронного ввода-вывода гораздо проще.  
  
 Начиная с [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], Visual Studio предоставляет два ключевых слова для асинхронного программирования:  
  
 Модификатор`Async` (Visual Basic) или `async` (C#), который используется для пометки метода, содержащего асинхронную операцию.  
  
 Оператор`Await` (Visual Basic) или `await` (C#), который применяется к результату асинхронного метода.  
  
 Для реализации операций асинхронного ввода-вывода используйте эти ключевые слова в сочетании с асинхронными методами, как показано в следующих примерах. Дополнительные сведения см. в разделе [Асинхронное программирование с использованием ключевых слов async и await](https://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7).  
  
 Следующий пример демонстрирует использование двух объектов <xref:System.IO.FileStream> для асинхронного копирования файлов из одного каталога в другой. Обратите внимание, что обработчик событий <xref:System.Web.UI.WebControls.Button.Click> для элемента управления <xref:System.Windows.Controls.Button> помечается с помощью модификатора `async` , так как вызывает асинхронный метод.  
  
 [!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
 [!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]  
  
 Следующий пример похож на предыдущий, но использует объекты <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter> для чтения и записи содержимого текстового файла в асинхронном режиме.  
  
 [!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
 [!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]  
  
 В следующем примере показан файл кода программной части и XAML-файл, которые используются, чтобы открыть файл в виде <xref:System.IO.Stream> в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] и считать его содержимое с помощью экземпляра класса <xref:System.IO.StreamReader> . Здесь асинхронные методы используются для открытия файла в виде потока и чтения его содержимого.  
  
 [!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
 [!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]  
  
 [!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.Stream>  
 [Файловый и потоковый ввод-вывод](../../../docs/standard/io/index.md)  
 [Асинхронное программирование с использованием ключевых слов Async и Await](https://msdn.microsoft.com/library/db854f91-ccef-4035-ae4d-0911fde808c7)
