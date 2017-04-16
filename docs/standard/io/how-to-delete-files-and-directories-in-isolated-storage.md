---
title: "Практическое руководство. Удаление файлов и каталогов из изолированного хранилища | Microsoft Docs"
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
  - "хранение данных с помощью изолированного хранилища, удаление файлов и папок"
  - "каталоги [платформа .NET Framework], изолированное хранилище"
  - "файлы [платформа .NET Framework], изолированное хранилище"
  - "изолированное хранилище, удаление файлов и папок"
  - "хранилища данных, удаление файлов и папок"
  - "хранилища, создание файлов и папок"
  - "удаление файлов в файле изолированного хранилища"
  - "сохранение данных с помощью изолированного хранилища, удаление файлов и папок"
  - "удаление каталогов в файле изолированного хранилища"
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Удаление файлов и каталогов из изолированного хранилища
Файлы и каталоги, расположенные внутри файла изолированного хранилища, можно удалять.  Имена хранилищ, файлов и каталогов зависят от операционной системы и указаны относительно корневого каталога виртуальной файловой системы.  Они не зависят от регистра в операционных системах Windows.  
  
 Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName> предоставляет два метода для удаления каталогов и файлов: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.  При попытке удаления несуществующего файла или каталога создается исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  При включении подстановочных знаков в имени <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> вызывает исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>, а <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> вызывает исключение <xref:System.ArgumentException>.  
  
 Если каталог содержит файлы или вложенные каталоги, то при вызове метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> возникает ошибка.  Можно использовать методы <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> для получения существующих файлов и каталогов.  Дополнительные сведения о поиске виртуальной файловой системы хранилища см. в разделе [Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## Пример  
 В следующем примере кода создается и удаляется ряд файлов и каталогов.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=fullName>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)