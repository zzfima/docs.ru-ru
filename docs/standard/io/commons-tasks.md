---
title: "Распространенные задачи ввода-вывода | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Ввод и вывод, общие задачи"
ms.assetid: bf00c380-706a-4e38-b829-454a480629fc
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
---
# Распространенные задачи ввода-вывода
Пространство имен <xref:System.IO> предоставляет несколько классов, которые позволяют выполнять с файлами, каталогами и потоками различные действия, такие как чтение и запись.  Дополнительные сведения см. в разделе [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md).  
  
## Распространенные задачи с файлами  
  
|Действие|Раздел с примером|  
|--------------|-----------------------|  
|Создание текстового файла|Метод <xref:System.IO.File.CreateText%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.CreateText%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.File.Create%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.Create%2A?displayProperty=fullName>|  
|Запись в текстовый файл|[Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)<br /><br /> [Практическое руководство. Запись данных в текстовый файл](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md)|  
|Чтение из текстового файла|[Практическое руководство. Считывание текста из файла](../../../docs/standard/io/how-to-read-text-from-a-file.md)|  
|Добавление текста в файл|[Практическое руководство. Открытие файла журнала и добавление в него данных](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)<br /><br /> Метод <xref:System.IO.File.AppendText%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.AppendText%2A?displayProperty=fullName>|  
|Переименование или перемещение файла|Метод <xref:System.IO.File.Move%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.MoveTo%2A?displayProperty=fullName>|  
|Удаление файла|Метод <xref:System.IO.File.Delete%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.Delete%2A?displayProperty=fullName>|  
|Копирование файла|Метод <xref:System.IO.File.Copy%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.FileInfo.CopyTo%2A?displayProperty=fullName>|  
|Получение сведений о размере файла|Свойство <xref:System.IO.FileInfo.Length%2A?displayProperty=fullName>|  
|Получение атрибутов файла|Метод <xref:System.IO.File.GetAttributes%2A?displayProperty=fullName>|  
|Установка атрибутов файла|Метод <xref:System.IO.File.SetAttributes%2A?displayProperty=fullName>|  
|Определение существования файла|Метод <xref:System.IO.File.Exists%2A?displayProperty=fullName>|  
|Чтение из двоичного файла|[Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Запись в двоичный файл|[Практическое руководство. Считывание из нового файла данных и запись в этот файл](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)|  
|Извлечение расширения имени файла|Метод <xref:System.IO.Path.GetExtension%2A?displayProperty=fullName>|  
|Извлечение полного пути к файлу|Метод <xref:System.IO.Path.GetFullPath%2A?displayProperty=fullName>|  
|Извлечение имени и расширения файла из пути|Метод <xref:System.IO.Path.GetFileName%2A?displayProperty=fullName>|  
|Изменение расширения файла|Метод <xref:System.IO.Path.ChangeExtension%2A?displayProperty=fullName>|  
  
## Распространенные задачи с каталогами  
  
|Действие|Раздел с примером|  
|--------------|-----------------------|  
|Доступ к файлу в особой папке, например "Мои документы"|[Практическое руководство. Запись текста в файл](../../../docs/standard/io/how-to-write-text-to-a-file.md)|  
|Создание каталога|Метод <xref:System.IO.Directory.CreateDirectory%2A?displayProperty=fullName><br /><br /> Свойство <xref:System.IO.FileInfo.Directory%2A?displayProperty=fullName>|  
|Создание подкаталога|Метод <xref:System.IO.DirectoryInfo.CreateSubdirectory%2A?displayProperty=fullName>|  
|Переименование или перемещение каталога|Метод <xref:System.IO.Directory.Move%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.DirectoryInfo.MoveTo%2A?displayProperty=fullName>|  
|Копирование каталога|[Практическое руководство. Копирование каталогов](../../../docs/standard/io/how-to-copy-directories.md)|  
|Удаление каталога|Метод <xref:System.IO.Directory.Delete%2A?displayProperty=fullName><br /><br /> Метод <xref:System.IO.DirectoryInfo.Delete%2A?displayProperty=fullName>|  
|Просмотр файлов и подкаталогов в каталогах|[Практическое руководство. Перечисление каталогов и файлов](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)|  
|Определение размера каталога|Класс <xref:System.IO.Directory?displayProperty=fullName>|  
|Определение существования каталога|Метод <xref:System.IO.Directory.Exists%2A?displayProperty=fullName>|  
  
## См. также  
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)   
 [Составление потоков](../../../docs/standard/io/composing-streams.md)   
 [Асинхронный файловый ввод\-вывод](../../../docs/standard/io/асинхронный-файловый-ввод-вывод.md)