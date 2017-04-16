---
title: "Практическое руководство. Считывание текста из файла | Microsoft Docs"
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
  - "потоки данных, чтение текста из файлов"
  - "ввод-вывод [платформа .NET Framework], чтение текста из файлов"
  - "чтение данных, текстовые файлы"
  - "чтение текстовых файлов"
  - "потоки, чтение текста из файлов"
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
caps.latest.revision: 23
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 23
---
# Практическое руководство. Считывание текста из файла
В следующих примерах демонстрируется синхронное и асинхронное чтение текста из текстового файла с использованием .NET для классических приложений.  В обоих примерах при создании экземпляра класса <xref:System.IO.StreamReader> указывается относительный или абсолютный путь к файлу.  В следующих примерах предполагается, что файл с именем TestFile.txt находится в той же папке, что и приложение.  
  
 Эти примеры кода не относятся к разработке приложений для Магазина Windows, поскольку в среде выполнения Windows используются разные типы потоков для чтения и записи файлов.  Пример, в котором демонстрируется чтение текста из файла в контексте приложения Магазина Windows, см. в разделе [Краткое руководство: чтение и запись файлов](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx).  Примеры, демонстрирующие преобразование потоков .NET Framework в потоки среды выполнения Windows и наоборот, см. в разделе [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md).  
  
## Пример  
 Первый пример иллюстрирует синхронную операцию чтения в консольном приложении.  В этом примере текстовый файл открывается с помощью модуля чтения потока, содержимое копируется в строку, а строка выводится на консоль.  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source3.cs#3)]
 [!code-vb[Conceptual.BasicIO.TextFiles#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source3.vb#3)]  
  
## Пример  
 Второй пример иллюстрирует асинхронную операцию чтения в приложении Windows Presentation Foundation \(WPF\).  
  
 [!code-csharp[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source6.cs#6)]
 [!code-vb[Conceptual.BasicIO.TextFiles#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source6.vb#6)]  
  
## См. также  
 <xref:System.IO.StreamReader>   
 <xref:System.IO.File.OpenText%2A?displayProperty=fullName>   
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName>   
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/ru-ru/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [Краткое руководство: чтение и запись файлов](http://msdn.microsoft.com/library/windows/apps/hh758325.aspx)   
 [Практическое руководство. Преобразование между потоками .NET Framework и потоками среды выполнения Windows](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)   
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Практическое руководство. Считывание символов из строки](../../../docs/standard/io/how-to-read-characters-from-a-string.md)   
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)