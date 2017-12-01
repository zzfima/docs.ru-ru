---
title: "Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище"
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
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище
Поиск каталогов в изолированном хранилище, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> метод. Этот метод принимает строку, представляющую шаблон поиска. Можно использовать одного знака (?) и нескольких символов (*) подстановочные знаки в шаблон поиска, но символы-шаблоны, должен быть указан в последней части имени. Например `directory1/*ect*` имеет допустимую строку поиска, но `*ect*/directory2` не является.  
  
 Чтобы найти файл, используйте <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> метод. Ограничения проверки подстановочные знаки в строке поиска, к которым применяется <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> также применяется к <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Ни один из этих методов является рекурсивной. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> класс не предоставляет методы для перечисления всех каталогов или файлов в хранилище. Тем не менее в следующем примере кода показаны методы рекурсивной.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано создание файлов и каталогов в изолированном хранилище. Во-первых, извлекается и помещен в хранилище, — изолированное по пользователю, домену и сборке `isoStore` переменной. <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Метод используется для настройки нескольких разных каталогах и <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> конструктор создает некоторые файлы в этих каталогах. Затем код выполняет цикл по результатам `GetAllDirectories` метод. Этот метод использует <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> для поиска всех имен каталогов в текущем каталоге. Эти имена хранятся в виде массива, а затем `GetAllDirectories` вызывает себя, передавая в каждом каталоге, он найден. В результате всех имен каталогов, возвращаются в виде массива. Затем код вызывает `GetAllFiles` метод. Этот метод вызывает метод `GetAllDirectories` для поиска всех имен каталогов, а затем проверяет каждый каталог для файлов с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> метод. Результат возвращается в виде массива для вывода.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
