---
title: "Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище | Microsoft Docs"
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
  - "хранилища, поиск файлов и папок"
  - "поиск файлов в файле изолированного хранилища"
  - "каталоги [платформа .NET Framework], изолированное хранилище"
  - "изолированное хранилище, поиск файлов и папок"
  - "хранение данных с помощью изолированного хранилища, поиск файлов и папок"
  - "файлы [платформа .NET Framework], изолированное хранилище"
  - "хранилища данных, поиск файлов и папок"
  - "поиск каталогов в файле изолированного хранилища"
  - "сохранение данных с помощью изолированного хранилища, поиск файлов и папок"
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище
Для поиска каталога в изолированном хранилище используйте метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=fullName>.  Этот метод принимает строку, представляющую шаблон поиска.  В шаблоне поиска можно использовать как односимвольные \(?\), так и многосимвольные \(\*\) заполнители, но знаки заполнителя должны появляться в последней части имени.  Например, `directory1/*ect*` является допустимой строкой поиска, а `*ect*/directory2` не является.  
  
 Для поиска файла используйте метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=fullName>.  Ограничение подстановочных знаков в строке поиска, которое применяется к <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>, также применяется к <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Ни один из этих методов не является рекурсивным; класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> не предоставляет никаких методов для перечисления всех каталогов или файлов в хранилище.  Однако рекурсивные методы отображаются в следующем примере кода.  
  
## Пример  
 В следующем примере показано, как создавать файлы и каталоги в изолированном хранилище.  Сначала извлекается хранилище, изолированное для пользователя, домена и сборки, и помещается в переменную `isoStore`.  Затем для создания нескольких разных каталогов используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A>, а конструктор <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> создает несколько каталогов в этих папках.  После этого код реализует цикл по результатам, возвращаемым методом `GetAllDirectories`.  Этот метод использует <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> для поиска всех имен каталогов в текущей папке.  Эти имена сохраняются в массиве, а затем метод `GetAllDirectories` вызывает себя, передавая в качестве аргумента каждый из найденных каталогов.  Результатом является массив имен всех каталогов.  Затем код вызывает метод `GetAllFiles`.  Этот метод вызывает `GetAllDirectories` для поиска имен всех каталогов и затем ищет файлы во всех каталогах с помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  Результат возвращается в виде массива для вывода.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)