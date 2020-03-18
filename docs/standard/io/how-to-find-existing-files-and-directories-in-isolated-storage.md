---
title: Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: dfebcc9acf0b699f898c106921d15ce0294bc5d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75707137"
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a>Практическое руководство. Поиск существующих файлов и каталоги в изолированном хранилище

Чтобы выполнить поиск по каталогу в изолированном хранилище, используйте метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType>. Этот метод принимает строку, которая представляет шаблон для поиска. В шаблоне поиска вы можете использовать как одиночные (?), так и многосимвольные (\*) подстановочные знаки, но они должны находиться только в последней части имени. Например, допустимой строкой для поиска является `directory1/*ect*`, но не `*ect*/directory2`.  
  
 Чтобы выполнить поиск файла, используйте метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType>. Ограничение на использование подстановочных знаков в строках для поиска, которое задано для <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>, применяется и к <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.  
  
 Ни один из этих методов не является рекурсивным. Класс <xref:System.IO.IsolatedStorage.IsolatedStorageFile> не предоставляет никаких методов для перечисления всех каталогов или файлов в хранилище. Но в примере кода ниже мы предлагаем вам несколько рекурсивных методов.  
  
## <a name="example"></a>Пример  
 В примере кода ниже показано, как создавать файлы и каталоги в изолированном хранилище. Сначала код получает данные о хранилище, изолированном по пользователю, домену и сборке, и помещает его в переменную `isoStore`. С помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> создаются несколько разных каталогов, а конструктор <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> создает в них файлы. Затем код в цикле обрабатывает результаты выполнения метода `GetAllDirectories`. Этот метод использует <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> для поиска всех имен каталогов в текущем каталоге. Эти имена сохраняются в массиве, а затем `GetAllDirectories` вызывает сам себя и передает в качестве параметра каждый найденный каталог. В конечном счете возвращается массив с именами всех каталогов. Затем этот код вызывает метод `GetAllFiles`. Он, в свою очередь, вызывает `GetAllDirectories` для поиска всех имен каталогов и ищет файлы в каждом из каталогов с помощью метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>. Результат возвращается в виде массива для отображения.  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
