---
title: Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96067ab6c8e13417158e4ebf7fae0e08cb9fbea4
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087483"
---
# <a name="how-to-convert-between-net-framework-streams-and-windows-runtime-streams"></a>Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows

.NET Framework для приложений Магазина Windows — это подмножество полной платформы .NET Framework. Из-за требований к безопасности и другим аспектам в приложениях Магазина Windows нельзя использовать полный набор API платформы .NET Framework для открытия и чтения файлов. Дополнительные сведения см. в статье [Обзор .NET для приложений Магазина Windows](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Однако может потребоваться использовать API платформы .NET Framework для других операций обработки потока. Для работы с потоками может потребоваться выполнить преобразование между типом потока .NET Framework, таким как <xref:System.IO.MemoryStream> или <xref:System.IO.FileStream>, и потоком среды выполнения Windows, таким как <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> или <xref:Windows.Storage.Streams.IRandomAccessStream>.

Класс [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) содержит методы, которые позволяют легко выполнить эти преобразования. Однако существует ряд различий между потоками в платформе .NET Framework и среде выполнения Windows, которые влияют на результаты использования этих методов. Подробности описаны в следующих разделах.

## <a name="converting-from-a-windows-runtime-stream-to-a-net-framework-stream"></a>Преобразование потока среды выполнения Windows в поток .NET Framework

Поток среды выполнения Windows можно преобразовать в поток .NET Framework, используя один из следующих методов [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

[System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx)  
Преобразует поток прямого доступа в среде выполнения Windows в управляемый поток подмножества .NET для приложений Магазина Windows.

[System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforwrite.aspx)  
Преобразует выходной поток в среде выполнения Windows в управляемый поток подмножества .NET для приложений Магазина Windows.

[System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx)  
Преобразует входной поток в среде выполнения Windows в управляемый поток подмножества .NET для приложений Магазина Windows.

Среда выполнения Windows предлагает типы потоков, которые поддерживают только чтение, только запись или же чтение и запись, и эти возможности поддерживаются при преобразовании потока среды выполнения Windows в поток .NET Framework. Кроме того, при преобразовании потока среды выполнения Windows в поток .NET Framework и обратно можно получить исходный экземпляр среды выполнения Windows. Рекомендуется использовать метод преобразования, соответствующий возможностями потока среды выполнения Windows, который необходимо преобразовать. Однако поскольку поток <xref:Windows.Storage.Streams.IRandomAccessStream> поддерживает чтение и запись (реализует как <xref:Windows.Storage.Streams.IOutputStream>, так и <xref:Windows.Storage.Streams.IInputStream>), любые методы преобразования позволяют сохранить возможности исходного потока. Например, использование [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) для преобразования <xref:Windows.Storage.Streams.IRandomAccessStream> не ограничит возможности преобразованного потока .NET Framework только чтением, поддержка записи также сохранится.

### <a name="to-convert-from-a-windows-runtime-random-access-stream-to-a-net-framework-stream"></a>Инструкции по преобразованию потока среды выполнения Windows в поток .NET Framework

- Используйте метод [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx).

  В следующем примере кода показано, как предложить пользователю выбрать файл, открыть его с помощью API-интерфейсов среды выполнения Windows, а затем преобразовать его в поток платформы .NET Framework, который считывается и выводится в текстовый блок. В таких случаях перед выводом результатов обычно с помощью API-интерфейсов .NET Framework ведется работа с потоком.

  Для выполнения этого примера необходимо создать XAML-приложение Магазина Windows, которое содержит текстовый блок с именем `TextBlock1` и кнопку с именем  `Button1`. В этом примере событие нажатия кнопки должно быть связано с методом `button1_Click` .

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]
  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#1](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#1)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#1)]

## <a name="converting-from-a-net-framework-stream-to-a-windows-runtime-stream"></a>Преобразование потока .NET Framework в поток среды выполнения Windows

Поток .NET Framework можно преобразовать в поток среды выполнения Windows, используя один из следующих методов [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

[System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx): преобразует управляемый поток подмножества .NET для приложений Магазина Windows во входной поток в среде выполнения Windows.

[System.IO.WindowsRuntimeStreamExtensions.AsOutputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asoutputstream.aspx): преобразует управляемый поток подмножества .NET для приложений Магазина Windows в выходной поток в среде выполнения Windows.

[AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md): преобразует управляемый поток подмножества .NET для приложений Магазина Windows в поток прямого доступа, который можно использовать для чтения и записи в среде выполнения Windows.

При преобразовании потока .NET Framework в поток среды выполнения Windows возможности преобразованного потока зависят от исходного потока. Например, если исходный поток поддерживает чтение и запись, можно вызвать метод [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) для преобразования потока, после чего будет возвращен тип `IRandomAccessStream`, который реализует `IInputStream` и `IOutputStream` и поддерживает чтение и запись.

Потоки .NET Framework не поддерживают клонирование даже после преобразования. Это означает, что в случае преобразовании потока .NET Framework в поток среды выполнения Windows с последующим вызовом метода <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> или <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A>, который вызывает <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> или <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> напрямую, возникнет исключение.

### <a name="to-convert-from-a-net-framework-stream-to-a-windows-runtime-random-access-stream"></a>Инструкции по преобразованию потока .NET Framework в поток среды выполнения Windows

- Используйте метод [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md), как показано в следующем примере:

  > [!IMPORTANT]
  > Убедитесь, что используемый вами поток .NET Framework поддерживает поиск, или скопируйте его в поток, поддерживающий поиск. Чтобы это определить, используйте свойство <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType>.

  Для выполнения этого примера необходимо создать XAML-приложение Магазина Windows, предназначенное для .NET Framework 4.5.1 и содержащее текстовый блок с именем `TextBlock2` и кнопку с именем `Button2`. В этом примере событие нажатия кнопки должно быть связано с методом `button2_Click` .

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#imports)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#imports)]
  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#2](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage.xaml.cs#2)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage.xaml.vb#2)]

## <a name="see-also"></a>См. также

- [Краткое руководство. Чтение и запись файлов (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
- [Общие сведения о платформе .NET для приложений Магазина Windows](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
- [Поддерживаемые API .NET для приложений Магазина Windows](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)  