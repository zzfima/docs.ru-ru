---
title: "Практическое руководство. Считывание из файлов и запись в файлы в изолированном хранилище | Microsoft Docs"
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
  - "хранение данных с помощью изолированного хранилища, чтение и запись в файлы"
  - "хранилища данных, чтение и запись в файлы"
  - "файлы, изолированное хранилище"
  - "изолированное хранилище, чтение и запись в файлы"
  - "чтение данных"
  - "чтение файлов в хранилище"
  - "хранилища, чтение и запись в файлы"
  - "сохранение данных с помощью изолированного хранилища, чтение и запись в файлы"
  - "запись в файлы в хранилище"
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
caps.latest.revision: 15
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Считывание из файлов и запись в файлы в изолированном хранилище
Для чтения или записи в файл в изолированном хранилище, используйте объект <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> с модулем чтения потока \(объектом <xref:System.IO.StreamReader> \) или средство записи потока \(объекта <xref:System.IO.StreamWriter>\).  
  
## Пример  
 В следующем примере кода показано получение изолированного хранилища и проверка, существует ли файл с именем TestStore.txt в хранилище.  Если он не существует, создается файл и записывается "Hello Isolated Storage" в файл.  Если параметр TestStore.txt уже существует, то пример кода считывает данные из файла.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>   
 <xref:System.IO.FileMode?displayProperty=fullName>   
 <xref:System.IO.FileAccess?displayProperty=fullName>   
 <xref:System.IO.StreamReader?displayProperty=fullName>   
 <xref:System.IO.StreamWriter?displayProperty=fullName>   
 [Файловый и потоковый ввод\-вывод](../../../docs/standard/io/index.md)   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)