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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cf6295e7d58d03e7b4bf4e0a00cfc509d289e071
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Практическое руководство. Создание файлов и каталогов в изолированном хранилище
Получив изолированное хранилище, в нем можно создавать файлы и папки для хранения данных. В хранилище имена файлов и каталогов указываются относительно корня виртуальной файловой системы.  
  
 Чтобы создать каталог, используйте экземпляр метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>. Если вы укажете подкаталог в несуществующем каталоге, создаются оба этих каталога. Если вы укажете уже существующий каталог, метод сразу завершает работу, не создавая каталог и не вызывая исключений. Но если вы укажете в имени каталога недопустимые символы, создастся исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  
  
 Для создания файла используется метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.  
  
 В изолированных хранилищах на операционной системе Windows регистр в именах файлов и каталогов не учитывается. Таким образом, если попытаться создать файл с именем `ThisFile.txt` и еще один файл с именем `THISFILE.TXT`, будет создан только один файл. Имя файла отображается в том регистре, который был указан при создании файла.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создавать файлы и каталоги в изолированном хранилище.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
