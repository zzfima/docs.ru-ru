---
title: "Практическое руководство. Получение хранилищ для изолированного хранения | Microsoft Docs"
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
  - "хранилища, получение"
  - "сохранение данных с помощью изолированного хранилища, получение хранилищ"
  - "изолированное хранилище, получение хранилищ"
  - "хранилища данных, получение"
  - "хранение данных с помощью изолированного хранилища, получение хранилищ"
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: 19
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 19
---
# Практическое руководство. Получение хранилищ для изолированного хранения
Изолированное хранилище предоставляет доступ к виртуальной файловой системе внутри секции данных.  Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет несколько методов для взаимодействия с изолированным хранилищем.  Для создания и получения хранилищ, класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> предоставляет три статических метода:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A> возвращает хранилище, изолированное по пользователю или сборке.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> возвращает хранилище, изолированное по домену или сборке.  
  
     Оба метода возвращают хранилище, принадлежащие к коду, из которого они были вызваны.  
  
-   Статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> возвращает изолированное хранилище, указанное посредством передачи в него комбинации параметров области.  
  
 В следующем примере код возвращает хранилище, изолированное пользователем, сборкой и доменом.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Для указания необходимости перемещения хранилища вместе с перемещающимся профилем пользователя может использоваться метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  Сведения о том, как это установить, см. в разделе [Типы изоляции](../../../docs/standard/io/types-of-isolation.md).  
  
 Изолированные хранилища, полученные из разных сборок, по умолчанию являются разными хранилищами.  Доступ к хранилищу другой сборки или домена можно получить, передав свидетельства сборки или домена в параметрах метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  Для этого необходимо разрешение на доступ к изолированному хранилищу по идентификатору домена приложения.  Дополнительные сведения см. в описании перегрузки метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 Методы <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> возвращают объект <xref:System.IO.IsolatedStorage.IsolatedStorageFile>.  Дополнительные сведения о выборе наиболее подходящего типа изоляции см. в разделе [Типы изоляции](../../../docs/standard/io/types-of-isolation.md).  При получении объекта файла изолированного хранилища, можно использовать методы изолированного хранилища для чтения, записи, создания и удаления файлов и каталогов файлов.  
  
 Не существует механизма предотвращения передачи кодом объекта <xref:System.IO.IsolatedStorage.IsolatedStorageFile> коду, не имеющему прав доступа, необходимых для самостоятельного получения хранилища.  Идентификации доменов и сборок и разрешения изолированного хранения проверяются только при получении ссылки на объект <xref:System.IO.IsolatedStorage.IsolatedStorage>, обычно в методах <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  Таким образом, ответственность за защиту ссылок на объекты <xref:System.IO.IsolatedStorage.IsolatedStorageFile> несет код, использующий эти ссылки.  
  
## Пример  
 Следующий код предоставляет простой демонстрацией получения классом хранилища, изолированного по пользователю и сборке.  Код может быть изменен для получения хранилища, изолированного по пользователю, домену и сборке, путем добавления домена <xref:System.IO.IsolatedStorage.IsolatedStorageScope?displayProperty=fullName> к аргументам, передающимся методу <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  
  
 После выполнения кода можно убедиться, что хранилище создано, набрав **StoreAdm \/LIST** в командной строке.  Эта команда вызывает программу [Средство изолированного хранения \(Storeadm.exe\)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) и выводит все текущие изолированные хранилища пользователя.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)   
 [Типы изоляции](../../../docs/standard/io/types-of-isolation.md)   
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)