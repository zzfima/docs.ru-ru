---
title: "Практическое руководство. Создание файлов и каталогов в изолированном хранилище | Microsoft Docs"
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
  - "каталоги [платформа .NET Framework], изолированное хранилище"
  - "файлы [платформа .NET Framework], изолированное хранилище"
  - "изолированное хранилище, создание файлов и каталогов"
  - "хранилища данных, создание файлов и каталогов"
  - "хранение данных с помощью изолированного хранилища, создание файлов и каталогов"
  - "хранилища, создание файлов и каталогов"
  - "хранение данных с помощью изолированного хранилища, создание файлов и каталогов"
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание файлов и каталогов в изолированном хранилище
После получения изолированного хранилища в нем можно создавать каталоги и файлы для хранения данных.  Внутри хранилища имена каталогов и файлов указываются относительно корневого каталога виртуальной файловой системы.  
  
 Чтобы создать каталог, используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=fullName> экземпляра .  Если указывается подкаталог еще не созданного каталога, то создаются оба каталога.  Если указывается уже существующий каталог, то метод возвращает управление без создания каталога, и исключение не создается.  Однако, если указано имя каталога, которое содержит недопустимые знаки, то создается исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  
  
 Для создания файла используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=fullName>.  
  
 В операционной системе Windows имена файлов и каталогов в изолированном хранилище не чувствительны к регистру.  Таким образом, если создать файл с именем `ThisFile.txt`, а затем создать другой файл с именем `THISFILE.TXT`, то будет создан только один файл.  При отображении сохраняется исходный регистр имени файла.  
  
## Пример  
 В следующем примере показано, как создавать файлы и каталоги в изолированном хранилище.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)