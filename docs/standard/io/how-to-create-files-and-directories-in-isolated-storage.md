---
title: "Практическое руководство. Создание файлов и каталогов в изолированном хранилище"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Практическое руководство. Создание файлов и каталогов в изолированном хранилище
После получения изолированного хранилища, можно создать файлы и папки для хранения данных. Внутри хранилища имена файлов и каталогов указываются относительно корневого каталога виртуальной файловой системы.  
  
 Чтобы создать каталог, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> метод экземпляра. Если указать подкаталог каталога, который не существует, создаются обоих служб каталогов. Если задан каталог, который уже существует, метод возвращается без создания каталога и исключение не возникает. Тем не менее, если указать имя каталога, которое содержит недопустимые знаки <xref:System.IO.IsolatedStorage.IsolatedStorageException> исключения.  
  
 Для создания файла используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.  
  
 В операционной системе Windows, изолированное хранилище файлов и каталогов именах не учитывается регистр. То есть если создается файл с именем `ThisFile.txt`и создайте другой файл с именем `THISFILE.TXT`, создается только один файл. Имя файла сохраняется исходный регистр в целях отображения.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано создание файлов и каталогов в изолированном хранилище.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
