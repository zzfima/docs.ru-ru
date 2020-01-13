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
ms.openlocfilehash: 66e7d01f37a1119b9d2076a9131aa40f26d15625
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708195"
---
# <a name="asynchronous-file-io"></a>Асинхронный файловый ввод-вывод

Асинхронные операции позволяют выполнять ресурсоемкие операции ввода-вывода без блокировки основного потока. Это соображение, связанное с производительностью, особенно важно в приложениях Магазина Windows 8.x и классических приложениях, в которых длительная потоковая операция может блокировать поток пользовательского интерфейса и создавать впечатление, что приложение не работает.

Начиная с .NET Framework 4.5 для упрощения асинхронных операций типы ввода-вывода включают в себя асинхронные методы. Асинхронный метод содержит `Async` в своем имени, например <xref:System.IO.Stream.ReadAsync%2A>, <xref:System.IO.Stream.WriteAsync%2A>, <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.TextReader.ReadLineAsync%2A>и <xref:System.IO.TextReader.ReadToEndAsync%2A>. Эти асинхронные методы реализуются на базе классов потоков, таких как <xref:System.IO.Stream>, <xref:System.IO.FileStream>и <xref:System.IO.MemoryStream>, а также классов, используемых для чтения или записи данных в потоках, таких как <xref:System.IO.TextReader> и <xref:System.IO.TextWriter>.

В платформе .NET Framework 4 и более ранних версий для реализации операций асинхронного ввода-вывода необходимо использовать такие методы, как <xref:System.IO.Stream.BeginRead%2A> и <xref:System.IO.Stream.EndRead%2A> . Эти методы по-прежнему доступны в .NET Framework 4.5 для поддержки устаревшего кода. Однако асинхронные методы позволяют реализовать операции асинхронного ввода-вывода гораздо проще.

Языки C# и Visual Basic имеют по два ключевых слова для асинхронного программирования:

- Модификатор`Async` (Visual Basic) или `async` (C#), который используется для пометки метода, содержащего асинхронную операцию.

- Оператор`Await` (Visual Basic) или `await` (C#), который применяется к результату асинхронного метода.

Для реализации операций асинхронного ввода-вывода используйте эти ключевые слова в сочетании с асинхронными методами, как показано в следующих примерах. Дополнительные сведения см. в статье [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../csharp/programming-guide/concepts/async/index.md) или статье [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md).

Следующий пример демонстрирует использование двух объектов <xref:System.IO.FileStream> для асинхронного копирования файлов из одного каталога в другой. Обратите внимание, что обработчик событий <xref:System.Web.UI.WebControls.Button.Click> для элемента управления <xref:System.Windows.Controls.Button> помечается с помощью модификатора `async` , так как вызывает асинхронный метод.

[!code-csharp[Asynchronous_File_IO_async#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example.cs#1)]
[!code-vb[Asynchronous_File_IO_async#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example.vb#1)]

Следующий пример похож на предыдущий, но использует объекты <xref:System.IO.StreamReader> и <xref:System.IO.StreamWriter> для чтения и записи содержимого текстового файла в асинхронном режиме.

[!code-csharp[Asynchronous_File_IO_async#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Asynchronous_File_IO_async/cs/example2.cs#2)]
[!code-vb[Asynchronous_File_IO_async#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Asynchronous_File_IO_async/vb/example2.vb#2)]

В приведенном ниже примере показан файл кода программной части и XAML-файл, которые используются, чтобы открыть файл в виде <xref:System.IO.Stream> в приложении Магазина Windows 8.x и считать его содержимое с помощью экземпляра класса <xref:System.IO.StreamReader>. Здесь асинхронные методы используются для открытия файла в виде потока и чтения его содержимого.

[!code-csharp[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml.cs#2)]
[!code-vb[System.IO.WindowsRuntimeStorageExtensions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/vb/blankpage.xaml.vb#2)]

[!code-xaml[System.IO.WindowsRuntimeStorageExtensions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestorageextensions/cs/blankpage.xaml#1)]

## <a name="see-also"></a>См. также

- <xref:System.IO.Stream>
- [Файловый и потоковый ввод-вывод](index.md)
- [Асинхронное программирование с использованием ключевых слов Async и Await (C#)](../../csharp/programming-guide/concepts/async/index.md)
- [Асинхронное программирование с использованием ключевых слов Async и Await (Visual Basic)](../../visual-basic/programming-guide/concepts/async/index.md)
