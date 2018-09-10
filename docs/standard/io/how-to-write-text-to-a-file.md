---
title: Практическое руководство. Запись текста в файл
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70b2d04f381fdbc1ae47b1c90649df045e111afa
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484783"
---
# <a name="how-to-write-text-to-a-file"></a><span data-ttu-id="f42cb-102">Практическое руководство. Запись текста в файл</span><span class="sxs-lookup"><span data-stu-id="f42cb-102">How to: Write Text to a File</span></span>
<span data-ttu-id="f42cb-103">В этом разделе показаны различные способы, которыми можно записать текст в файл для приложений .NET Framework или приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f42cb-103">This topic shows different ways you can write text to a file for .NET Framework applications or [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="f42cb-104">Для записи текста в файл обычно используются следующие классы и методы.</span><span class="sxs-lookup"><span data-stu-id="f42cb-104">The following classes and methods are typically used to write text to a file:</span></span>  
  
-   <span data-ttu-id="f42cb-105"><xref:System.IO.StreamWriter> — содержит методы для записи в файл синхронно (<xref:System.IO.StreamWriter.Write%2A> или <xref:System.IO.TextWriter.WriteLine%2A>) или асинхронно (<xref:System.IO.StreamWriter.WriteAsync%2A> и <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span><span class="sxs-lookup"><span data-stu-id="f42cb-105"><xref:System.IO.StreamWriter> - it contains methods to write to a file synchronously (<xref:System.IO.StreamWriter.Write%2A> or <xref:System.IO.TextWriter.WriteLine%2A>) or asynchronously (<xref:System.IO.StreamWriter.WriteAsync%2A> and <xref:System.IO.StreamWriter.WriteLineAsync%2A>).</span></span>  
  
-   <span data-ttu-id="f42cb-106"><xref:System.IO.File> — используется с приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f42cb-106"><xref:System.IO.File> – to be used with .NET Framework applications.</span></span> <span data-ttu-id="f42cb-107">Он предоставляет статические методы для записи текста в файл, такие как <xref:System.IO.File.WriteAllLines%2A> и <xref:System.IO.File.WriteAllText%2A>, или для добавления текста в файл (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> или <xref:System.IO.File.AppendText%2A>).</span><span class="sxs-lookup"><span data-stu-id="f42cb-107">It provides static methods to write text to a file such as <xref:System.IO.File.WriteAllLines%2A> and <xref:System.IO.File.WriteAllText%2A>, or to append text to a file (<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> or <xref:System.IO.File.AppendText%2A>).</span></span>  
  
-   <span data-ttu-id="f42cb-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) — для использования с приложениями [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f42cb-108">[FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) - to be used with [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span> <span data-ttu-id="f42cb-109">Он содержит асинхронные методы для записи текста в файл ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) или [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) или добавления текста в файл ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) или [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span><span class="sxs-lookup"><span data-stu-id="f42cb-109">It contains asynchronous methods to write text to a file ([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) or [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)) or to append text to a file ([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) or [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)).</span></span>  

- <span data-ttu-id="f42cb-110"><xref:System.IO.Path> — для использования со строками, содержащими сведения о пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="f42cb-110"><xref:System.IO.Path> - to be used on strings that contain file or directory path information.</span></span> <span data-ttu-id="f42cb-111">Он содержит метод <xref:System.IO.Path.Combine%2A>, который позволяет объединять строки для создания пути к файлу или каталогу.</span><span class="sxs-lookup"><span data-stu-id="f42cb-111">It contains the <xref:System.IO.Path.Combine%2A> method, which allows concatenation of strings to build a file or directory path.</span></span>


 <span data-ttu-id="f42cb-112">Примеры довольно просты, чтобы сосредоточить внимание на выполняемой задаче.</span><span class="sxs-lookup"><span data-stu-id="f42cb-112">The samples have been kept simple in order to focus on the task being performed.</span></span> <span data-ttu-id="f42cb-113">По этой причине в этих примерах проверка ошибок и обработка исключений выполняется в минимальном объеме или отсутствует вовсе.</span><span class="sxs-lookup"><span data-stu-id="f42cb-113">For this reason, the samples perform minimal error checking and exception handling, if any.</span></span> <span data-ttu-id="f42cb-114">Реальное приложение обычно обеспечивает более надежную проверку ошибок и обработку исключений.</span><span class="sxs-lookup"><span data-stu-id="f42cb-114">A real-world application generally provides more robust error checking and exception handling.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42cb-115">Пример</span><span class="sxs-lookup"><span data-stu-id="f42cb-115">Example</span></span>  
 <span data-ttu-id="f42cb-116">В следующем примере показано, как синхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> по одной строке за раз.</span><span class="sxs-lookup"><span data-stu-id="f42cb-116">The following example shows how to synchronously write text to a new file using the <xref:System.IO.StreamWriter> class, one line at a time.</span></span> <span data-ttu-id="f42cb-117">Новый текстовый файл сохраняется в пользовательской папке "Мои документы".</span><span class="sxs-lookup"><span data-stu-id="f42cb-117">The new text file is saved to the user's My Documents folder.</span></span> <span data-ttu-id="f42cb-118">Поскольку объект <xref:System.IO.StreamWriter> объявляется и создается в инструкции `using` , вызывается метод <xref:System.IO.StreamWriter.Dispose%2A> , который автоматически выполняет очистку и закрывает поток.</span><span class="sxs-lookup"><span data-stu-id="f42cb-118">Because the <xref:System.IO.StreamWriter> object is declared and instantiated in a `using` statement, the <xref:System.IO.StreamWriter.Dispose%2A> method is invoked which automatically flushes and closes the stream.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  
  
## <a name="example"></a><span data-ttu-id="f42cb-119">Пример</span><span class="sxs-lookup"><span data-stu-id="f42cb-119">Example</span></span>  
 <span data-ttu-id="f42cb-120">В следующем примере показано, как добавить текст в существующий файл с помощью класса <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="f42cb-120">The following example shows how to append text to an existing file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="f42cb-121">В нем используется текстовый файл из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="f42cb-121">It uses the same text file from the previous example.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]     
  
## <a name="example"></a><span data-ttu-id="f42cb-122">Пример</span><span class="sxs-lookup"><span data-stu-id="f42cb-122">Example</span></span>  
 <span data-ttu-id="f42cb-123">В следующем примере показано, как асинхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="f42cb-123">The following example shows how to asynchronously write text to a new file using the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="f42cb-124">Для вызова метода <xref:System.IO.StreamWriter.WriteAsync%2A> этот вызов должен быть в методе `async` .</span><span class="sxs-lookup"><span data-stu-id="f42cb-124">In order to invoke the <xref:System.IO.StreamWriter.WriteAsync%2A> method, the method call needs to be within an `async` method.</span></span> <span data-ttu-id="f42cb-125">Новый текстовый файл сохраняется в пользовательской папке "Мои документы".</span><span class="sxs-lookup"><span data-stu-id="f42cb-125">The new text file is saved to the user's My Documents folder.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## <a name="example"></a><span data-ttu-id="f42cb-126">Пример</span><span class="sxs-lookup"><span data-stu-id="f42cb-126">Example</span></span>  
 <span data-ttu-id="f42cb-127">В следующем примере показано, как записать текст в новый файл и добавить новые строки текста в тот же файл с помощью класса <xref:System.IO.File> .</span><span class="sxs-lookup"><span data-stu-id="f42cb-127">The following example shows how to write text to a new file and append new lines of text to the same file using the <xref:System.IO.File> class.</span></span> <span data-ttu-id="f42cb-128">Методы <xref:System.IO.File.WriteAllText%2A> и <xref:System.IO.File.AppendAllLines%2A> открывают и закрывают файл автоматически.</span><span class="sxs-lookup"><span data-stu-id="f42cb-128">The <xref:System.IO.File.WriteAllText%2A> and <xref:System.IO.File.AppendAllLines%2A> methods open and close the file automatically.</span></span> <span data-ttu-id="f42cb-129">Если предоставленный в метод <xref:System.IO.File.WriteAllText%2A> путь уже существует, файл будет перезаписан.</span><span class="sxs-lookup"><span data-stu-id="f42cb-129">If the path you provide to the <xref:System.IO.File.WriteAllText%2A> method already exists, the file will be overwritten.</span></span>  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)] 
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## <a name="example"></a><span data-ttu-id="f42cb-130">Пример</span><span class="sxs-lookup"><span data-stu-id="f42cb-130">Example</span></span>  
 <span data-ttu-id="f42cb-131">В следующем примере показано, как асинхронно записать введенные пользователем данные в текстовый файл в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f42cb-131">The following example shows how to asynchronously write user input to a text file in a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app.</span></span> <span data-ttu-id="f42cb-132">По соображениям безопасности для открытия файла из [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения обычно требуется использование элемента управления [FileOpenPicker](https://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx).</span><span class="sxs-lookup"><span data-stu-id="f42cb-132">Because of security considerations, opening a file from a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app typically requires the use of a [FileOpenPicker](https://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx) control.</span></span> <span data-ttu-id="f42cb-133">В этом примере `FileOpenPicker` фильтруется для отображения текстовых файлов.</span><span class="sxs-lookup"><span data-stu-id="f42cb-133">In this example, the `FileOpenPicker` is filtered to show text files.</span></span>  
  
```xaml  
<Page  
    x:Class="OpenFileWindowsStore.MainPage"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    xmlns:local="using:OpenFileWindowsStore"  
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"  
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
    mc:Ignorable="d">  
  
    <Grid Background="{ThemeResource ApplicationPageBackgroundThemeBrush}">  
        <Button Content="save text to a file" HorizontalAlignment="Left" Margin="103,417,0,0" VerticalAlignment="Top"   
                Width="329" Height="86" FontSize="35" Click="Button_Click"/>  
        <TextBox Name="UserInputTextBox"  FontSize="18" HorizontalAlignment="Left" Margin="106,146,0,0"   
                 TextWrapping="Wrap" Text="Write some text here, and select a file to write it to." VerticalAlignment="Top"   
                 Height="201" Width="558" AcceptsReturn="True"/>  
        <TextBlock Name="StatusTextBox" HorizontalAlignment="Left" Margin="106,570,0,147" TextWrapping="Wrap" Text="Status:"   
                   VerticalAlignment="Center" Height="51" Width="1074" FontSize="18" />  
    </Grid>  
</Page>  
```  
  
 [!code-csharp[OpenFileWindowsStore#Code](../../../samples/snippets/csharp/VS_Snippets_CLR/openfilewindowsstore/cs/mainpage.xaml.cs#code)]
 [!code-vb[OpenFileWindowsStore#Code](../../../samples/snippets/visualbasic/VS_Snippets_CLR/openfilewindowsstore/vb/mainpage.xaml.vb#code)]  
  
## <a name="see-also"></a><span data-ttu-id="f42cb-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f42cb-134">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.Path>  
 <xref:System.IO.File.CreateText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="f42cb-135">Практическое руководство. Перечисление каталогов и файлов</span><span class="sxs-lookup"><span data-stu-id="f42cb-135">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="f42cb-136">Практическое руководство. Считывание из нового файла данных и запись в этот файл</span><span class="sxs-lookup"><span data-stu-id="f42cb-136">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="f42cb-137">Практическое руководство. Открытие файла журнала и добавление в него данных</span><span class="sxs-lookup"><span data-stu-id="f42cb-137">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="f42cb-138">Практическое руководство. Считывание текста из файла</span><span class="sxs-lookup"><span data-stu-id="f42cb-138">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="f42cb-139">Файловый и потоковый ввод-вывод</span><span class="sxs-lookup"><span data-stu-id="f42cb-139">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
