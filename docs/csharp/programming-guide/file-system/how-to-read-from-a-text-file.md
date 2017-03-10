---
title: "Практическое руководство. Чтение из текстового файла (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "StreamReader.ReadToEnd"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "чтение данных, текстовые файлы"
  - "чтение текстовых файлов"
  - "текстовые файлы, чтение"
  - "текстовые файлы, запись в"
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Практическое руководство. Чтение из текстового файла (Руководство по программированию на C#)
В этом примере производится чтение содержимого текстового файла с помощью статических методов <xref:System.IO.File.ReadAllText%2A> и <xref:System.IO.File.ReadAllLines%2A> от класса <xref:System.IO.File?displayProperty=fullName>.  
  
 Пример, использующий <xref:System.IO.StreamReader>, см. в разделе [Практическое руководство. Построчное чтение текстового файла](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md).  
  
> [!NOTE]
>  Файлы, которые используются в этом примере созданы в разделе [Практическое руководство. Запись в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md).  
  
## Пример  
 [!code-cs[csFilesandFolders#4](../../../csharp/programming-guide/file-system/codesnippet/csharp/csFilesFolders/FileIteration.cs#4)]  
  
## Компиляция кода  
 Скопируйте код и вставьте его в консольное приложение C\#.  
  
 Если не использовать текстовые файлы с [Практическое руководство. Запись в текстовый файл](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md), замените аргумента `ReadAllText` и `ReadAllLines` с соответствующим путем и имя файла на компьютере.  
  
## Отказоустойчивость  
 При следующих условиях возможно возникновение исключения.  
  
-   Файл не существует или не существует в указанном месте.  Проверьте правильность написания имени файла и путь к нему.  
  
## Безопасность платформы .NET Framework  
 Не следует полагаться на имя файла для определения содержимого файла.  Например, файл `myFile.cs` не может быть исходным файлом C\#.  
  
## См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр](../../../csharp/programming-guide/file-system/file-system-and-the-registry.md)