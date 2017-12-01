---
title: "Практическое руководство. Удаление файлов и каталогов из изолированного хранилища"
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
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a>Практическое руководство. Удаление файлов и каталогов из изолированного хранилища
Можно удалить файлы и папки внутри файла изолированного хранилища. Внутри хранилища имена файлов и каталогов, зависят от операционной системы и указан относительно корня виртуальной файловой системы. Они не учитывается в операционных системах Windows.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> Класс предоставляет два метода для удаления файлов и каталогов: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>. <xref:System.IO.IsolatedStorage.IsolatedStorageException> Исключение при попытке удалить файл или каталог, который не существует. При включении подстановочный знак в имени, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> вызывает <xref:System.IO.IsolatedStorage.IsolatedStorageException> исключение, и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> вызывает <xref:System.ArgumentException> исключение.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> Метод завершается ошибкой, если каталог содержит файлы или подкаталоги. Можно использовать <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> методы для получения существующих файлов и каталогов. Дополнительные сведения о поиске в виртуальной файловой системе хранилища см. в разделе [как: поиск существующих файлов и каталогов в изолированном хранилище](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода создается, а затем удаляет несколько каталогов и файлов.  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
