---
title: Как выполнить  Преобразование между потоками .NET Framework и потоками среды выполнения Windows (только в Windows)
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 23a763ea-8348-4244-9f8c-a4280b870b47
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dc38e69a79af7c7220b8e3b55d4cb1f4ca3695f6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255202"
---
# <a name="how-to-convert-between-net-framework-and-windows-runtime-streams-windows-only"></a>Как выполнить  Преобразование между потоками .NET Framework и потоками среды выполнения Windows (только в Windows)

.NET Framework для приложений UWP — это подмножество полной платформы .NET Framework. Из-за требований к безопасности и другим аспектам в приложениях UWP нельзя использовать полный набор API платформы .NET Framework для открытия и чтения файлов. Дополнительные сведения см. в статье [Обзор .NET для приложений UWP](https://docs.microsoft.com/previous-versions/windows/apps/br230302(v=vs.140)). Однако может потребоваться использовать API платформы .NET Framework для других операций обработки потока. Для работы с потоками вы можете выполнить преобразование между типом потока .NET Framework, таким как <xref:System.IO.MemoryStream> или <xref:System.IO.FileStream>, и потоком среды выполнения Windows, таким как <xref:Windows.Storage.Streams.IInputStream>, <xref:Windows.Storage.Streams.IOutputStream> или <xref:Windows.Storage.Streams.IRandomAccessStream>.

Класс [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx) содержит методы, которые позволяют легко выполнить эти преобразования. Однако различия между потоками на платформе .NET Framework и в среде выполнения Windows влияют на результаты использования этих методов, как описано в следующих разделах:

## <a name="convert-from-a-windows-runtime-to-a-net-framework-stream"></a>Преобразование потока среды выполнения Windows в поток .NET Framework
Поток среды выполнения Windows можно преобразовать в поток .NET Framework, используя один из следующих методов [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

- [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx) преобразует поток с прямым доступом в среде выполнения Windows в управляемый поток .NET для приложений UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForWrite](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforwrite.aspx) преобразует выходной поток в среде выполнения Windows в управляемый поток .NET для приложений UWP.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) преобразует входной поток в среде выполнения Windows в управляемый поток .NET для приложений UWP.

Среда выполнения Windows предлагает типы потоков, которые поддерживают только чтение, только запись или чтение и запись. Эти возможности поддерживаются при преобразовании потока среды выполнения Windows в поток .NET Framework. Кроме того, при преобразовании потока среды выполнения Windows в поток .NET Framework и обратно можно получить исходный экземпляр среды выполнения Windows. 

Рекомендуется использовать метод преобразования, соответствующий возможностям потока среды выполнения Windows, который необходимо преобразовать. Но поскольку поток <xref:Windows.Storage.Streams.IRandomAccessStream> поддерживает чтение и запись (реализует как <xref:Windows.Storage.Streams.IOutputStream>, так и <xref:Windows.Storage.Streams.IInputStream>), любые методы преобразования позволяют сохранить возможности исходного потока. Например, использование [System.IO.WindowsRuntimeStreamExtensions.AsStreamForRead](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstreamforread.aspx) для преобразования <xref:Windows.Storage.Streams.IRandomAccessStream> не ограничит возможности преобразованного потока .NET Framework только чтением. Он также доступен для записи.

## <a name="example-convert-windows-runtime-random-access-to-net-framework-stream"></a>Пример Преобразование потока среды выполнения Windows с прямым доступом в поток .NET Framework
Поток среды выполнения Windows с прямым доступом можно преобразовать в поток .NET Framework с помощью метода [System.IO.WindowsRuntimeStreamExtensions.AsStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asstream.aspx).

В следующем примере кода вам будет предложено выбрать файл, он откроется с API среды выполнения Windows, а затем преобразуется в поток .NET Framework. Поток считывается и выводится в текстовый блок. Обычно вы работаете с потоком с помощью API .NET Framework, прежде чем вывести результаты.

Для выполнения этого примера создайте XAML-приложение UWP, которое содержит текстовый блок с именем `TextBlock1` и кнопку с именем `Button1`. Свяжите событие нажатия кнопки с методом `button1_Click`, как показано в примере.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage1.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage1.xaml.vb)]

## <a name="convert-from-a-net-framework-to-a-windows-runtime-stream"></a>Преобразование потока .NET Framework в поток среды выполнения Windows
Поток .NET Framework можно преобразовать в поток среды выполнения Windows с помощью одного из следующих методов [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx):

- [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) преобразует управляемый поток .NET для приложений UWP во входной поток в среде выполнения Windows.
  
- [System.IO.WindowsRuntimeStreamExtensions.AsOutputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asoutputstream.aspx) преобразует управляемый поток .NET для приложений UWP в выходной поток в среде выполнения Windows.
  
- [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md) преобразует управляемый поток .NET для приложений UWP в поток с прямым доступом, который можно использовать для чтения и записи в среде выполнения Windows.

При преобразовании потока .NET Framework в поток среды выполнения Windows возможности преобразованного потока зависят от исходного потока. Например, если исходный поток поддерживает чтение и запись, можно вызвать метод [System.IO.WindowsRuntimeStreamExtensions.AsInputStream](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.asinputstream.aspx) для преобразования потока, после чего будет возвращен тип `IRandomAccessStream`. `IRandomAccessStream` реализует `IInputStream` и `IOutputStream` и поддерживает чтение и запись.

Потоки .NET Framework не поддерживают клонирование даже после преобразования. В случае преобразования потока .NET Framework в поток среды выполнения Windows с последующим вызовом метода <xref:Windows.Storage.Streams.InMemoryRandomAccessStream.GetInputStreamAt%2A> или <xref:Windows.Storage.Streams.IRandomAccessStream.GetOutputStreamAt%2A>, который вызывает <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A>, или при вызове <xref:Windows.Storage.Streams.RandomAccessStreamOverStream.CloneStream%2A> напрямую, возникнет исключение.

## <a name="example-convert-net-framework-to-windows-runtime-random-access-stream"></a>Пример Преобразование потока .NET Framework в поток среды выполнения Windows с прямым доступом

Чтобы преобразовать поток .NET Framework в поток среды выполнения Windows с прямым доступом, используйте метод [AsRandomAccessStream](../../../docs/standard/cross-platform/windowsruntimestreamextensions-asrandomaccessstream-method.md), как показано в следующем примере:

> [!IMPORTANT]
> Убедитесь, что используемый вами поток .NET Framework поддерживает поиск, или скопируйте его в поток, поддерживающий поиск. Чтобы это определить, используйте свойство <xref:System.IO.Stream.CanSeek%2A?displayProperty=nameWithType> .

Для выполнения этого примера создайте XAML-приложение UWP, предназначенное для .NET Framework 4.5.1 и содержащее текстовый блок с именем `TextBlock2` и кнопку с именем `Button2`. Свяжите событие нажатия кнопки с методом `button2_Click`, как показано в примере.

  [!code-csharp[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/csharp/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/cs/mainpage2.xaml.cs)]
  [!code-vb[System.IO.WindowsRuntimeStreamExtensionsEx#Imports](~/samples/snippets/visualbasic/VS_Snippets_CLR_System/system.io.windowsruntimestreamextensionsex/vb/mainpage2.xaml.vb)]

## <a name="see-also"></a>См. также

- [Краткое руководство. Чтение и запись файла (Windows)](https://msdn.microsoft.com/library/windows/apps/hh464978.aspx)  
- [Общие сведения о платформе .NET для приложений Магазина Windows](https://msdn.microsoft.com/library/windows/apps/br230302.aspx)  
- [.NET для приложений магазина Windows: поддерживаемые API](https://msdn.microsoft.com/library/windows/apps/br230232.aspx)  
