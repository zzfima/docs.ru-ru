---
title: "Практическое руководство. Считывание символов из строки | Microsoft Docs"
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
  - "чтение знаков из строк"
  - "потоки данных, чтение знаков из строки"
  - "ввод-вывод [платформа .NET Framework], чтение знаков из строк"
  - "чтение данных, строки"
  - "потоки, чтение знаков из строки"
ms.assetid: 27ea5e52-6db8-42d8-980a-50bcfc7fd270
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Считывание символов из строки
В следующих примерах кода показано, как синхронно и асинхронно считывать символы из строки.  
  
## Пример  
 В этом примере производится считывание 13 символов из строки, их сохранение в массиве и отображение.  Затем происходит считывание оставшихся в строке символов, сохранение их в массиве, начиная с шестого элемента и отображение содержимого массива.  
  
 [!code-cpp[Conceptual.StringReader#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.stringreader/cpp/source.cpp#1)]
 [!code-csharp[Conceptual.StringReader#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source.cs#1)]
 [!code-vb[Conceptual.StringReader#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source.vb#1)]  
  
## Пример  
 В следующем примере асинхронно считываются все символы из элемента управления <xref:System.Windows.Controls.TextBox> и сохраняются в массиве.  Затем каждая буква или символ пробела асинхронно записываются в отдельную строку элемента управления <xref:System.Windows.Controls.TextBlock>, в конец которой добавляется символ разрыва строки.  
  
 [!code-csharp[Conceptual.StringReader#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.stringreader/cs/source2.cs#2)]
 [!code-vb[Conceptual.StringReader#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.stringreader/vb/source2.vb#2)]  
  
## См. также  
 <xref:System.IO.StringReader>   
 <xref:System.IO.StringReader.Read%2A?displayProperty=fullName>   
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)   
 [NIB: How to: Create a Directory Listing](http://msdn.microsoft.com/ru-ru/4d2772b1-b991-4532-a8a6-6ef733277e69)   
 [Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)   
 [Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)   
 [Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)   
 [Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)   
 [Практическое руководство. Запись символов в строку](../../../docs/standard/io/how-to-write-characters-to-a-string.md)   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)