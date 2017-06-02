---
title: "Практическое руководство. Запись текста в файл | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "запись текста в файлы"
  - "ввод-вывод [платформа .NET Framework], запись текста в файлы"
  - "потоки, запись текста в файлы"
  - "потоки данных, запись текста в файлы"
ms.assetid: 060cbe06-2adf-4337-9e7b-961a5c840208
caps.latest.revision: 29
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 29
---
# Практическое руководство. Запись текста в файл
В этом разделе показаны различные способы, которыми можно записать текст в файл для приложений .NET Framework или приложений [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Для записи текста в файл обычно используются следующие классы и методы.  
  
-   <xref:System.IO.StreamWriter> — содержит методы для записи в файл синхронно \(<xref:System.IO.StreamWriter.Write%2A> или <xref:System.IO.TextWriter.WriteLine%2A>\) или асинхронно \(<xref:System.IO.StreamWriter.WriteAsync%2A> и <xref:System.IO.StreamWriter.WriteLineAsync%2A>\).  
  
-   <xref:System.IO.File> — используется с приложениями .NET Framework. Он предоставляет статические методы для записи текста в файл, такие как <xref:System.IO.File.WriteAllLines%2A> и <xref:System.IO.File.WriteAllText%2A>, или для добавления текста в файл \(<xref:System.IO.File.AppendAllLines%2A>, <xref:System.IO.File.AppendAllText%2A> или <xref:System.IO.File.AppendText%2A>\).  
  
-   [FileIO](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.aspx) — для использования с приложениями [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. Он содержит асинхронные методы для записи текста в файл \([WriteLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writelinesasync.aspx) или [WriteTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.writetextasync.aspx)\) или добавления текста в файл \([AppendLinesAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendlinesasync.aspx) или [AppendTextAsync](https://msdn.microsoft.com/library/windows/apps/windows.storage.fileio.appendtextasync.aspx)\).  
  
 Примеры довольно просты, чтобы сосредоточить внимание на выполняемой задаче. По этой причине в этих примерах проверка ошибок и обработка исключений выполняется в минимальном объеме или отсутствует вовсе. Реальное приложение обычно обеспечивает более надежную проверку ошибок и обработку исключений.  
  
## Пример  
 В следующем примере показано, как синхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter> по одной строке за раз. Новый текстовый файл сохраняется в пользовательской папке "Мои документы". Поскольку объект <xref:System.IO.StreamWriter> объявляется и создается в инструкции `using`, вызывается метод <xref:System.IO.StreamWriter.Dispose%2A>, который автоматически выполняет очистку и закрывает поток.  
  
 <!-- TODO: review snippet reference [!code-csharp[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeline)]  -->
 <!-- TODO: review snippet reference [!code-vb[Conceptual.BasicIO.TextFiles#WriteLine](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeline)]  -->  
  
## Пример  
 В следующем примере показано, как добавить текст в существующий файл с помощью класса <xref:System.IO.StreamWriter>. В нем используется текстовый файл из предыдущего примера.  
  
 <!-- TODO: review snippet reference [!code-csharp[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#appendtext)]  -->
 <!-- TODO: review snippet reference [!code-vb[Conceptual.BasicIO.TextFiles#AppendText](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#appendtext)]  -->  
  
## Пример  
 В следующем примере показано, как асинхронно записать текст в новый файл с помощью класса <xref:System.IO.StreamWriter>. Для вызова метода <xref:System.IO.StreamWriter.WriteAsync%2A> этот вызов должен быть в методе `async`. Новый текстовый файл сохраняется в пользовательской папке "Мои документы".  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writeasync)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteAsync](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writeasync)]  
  
## Пример  
 В следующем примере показано, как записать текст в новый файл и добавить новые строки текста в тот же файл с помощью класса <xref:System.IO.File>. Методы <xref:System.IO.File.WriteAllText%2A> и <xref:System.IO.File.AppendAllLines%2A> открывают и закрывают файл автоматически. Если предоставленный в метод <xref:System.IO.File.WriteAllText%2A> путь уже существует, файл будет перезаписан.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source.cs#writefile)]
 [!code-vb[Conceptual.BasicIO.TextFiles#WriteFile](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source.vb#writefile)]  
  
## Пример  
 В следующем примере показано, как асинхронно записать введенные пользователем данные в текстовый файл в приложении [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]. По соображениям безопасности для открытия файла из [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения обычно требуется использование элемента управления [FileOpenPicker](http://msdn.microsoft.com/library/windows/apps/windows.storage.pickers.fileopenpicker.aspx). В этом примере `FileOpenPicker` фильтруется для отображения текстовых файлов.  
  
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
  
## См. также  
 <xref:System.IO.StreamWriter>   
 <xref:System.IO.File.CreateText%2A?displayProperty=fullName>   
 [Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)   
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)