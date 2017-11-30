---
title: "Практическое руководство. Получение хранилищ для изолированного хранения"
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
- stores, obtaining
- storing data using isolated storage, obtaining stores
- isolated storage, obtaining stores
- data stores, obtaining
- data storage using isolated storage, obtaining stores
ms.assetid: fcb6b178-d526-47c4-b029-e946f880f9db
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb0b877aa0f4cee36bd1f8c1cea624cf9368fbaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-stores-for-isolated-storage"></a>Практическое руководство. Получение хранилищ для изолированного хранения
Изолированное хранилище предоставляет виртуальную файловую систему в ячейке данных. <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Класс предоставляет ряд методов для взаимодействия с помощью изолированного хранилища. Для создания и получения хранилищ <xref:System.IO.IsolatedStorage.IsolatedStorageFile> содержит три статических методов:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>Возвращает хранилища, изолированного по пользователю и сборке.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>Возвращает хранилища, в котором изолирована, домена и сборки.  
  
     Оба метода получения хранилища, к которому принадлежит код, из которого они вызываются.  
  
-   Статический метод <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> Возвращает изолированное хранилище, указанное посредством передачи в комбинации параметров области.  
  
 Следующий код возвращает хранилища, изолированного по пользователю, сборке и домену.  
  
 [!code-cpp[Conceptual.IsolatedStorage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#6)]
 [!code-csharp[Conceptual.IsolatedStorage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#6)]
 [!code-vb[Conceptual.IsolatedStorage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#6)]  
  
 Можно использовать <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод, чтобы указать, что хранилище должно перемещаться вместе с перемещаемым профилем пользователя. Дополнительные сведения о том, как настроить эту функцию, в разделе [типа изоляции](../../../docs/standard/io/types-of-isolation.md).  
  
 Изолированные хранилища, полученные из разных сборок, по умолчанию, различные хранилища. Можно использовать хранилище другой сборки или домена путем передачи в свидетельство сборки или домена в параметрах <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод. Это разрешение для доступа к изолированному хранилищу по идентификатору домена приложения. Дополнительные сведения см. в разделе <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> перегруженных версий метода.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, И <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> методы возвращают <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объекта. Сведения о выборе типа изоляции лучше всего подходит для конкретной ситуации, в разделе [типа изоляции](../../../docs/standard/io/types-of-isolation.md). При наличии объект файла изолированного хранилища, можно использовать методы изолированного хранилища для чтения, записи, создания и удаления файлов и каталогов.  
  
 Отсутствует механизм предотвращения передачи кодом <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объект на код, который не имеет необходимых прав доступа для получения само хранилище. Идентификаторы доменов и сборок и разрешения изолированного хранения проверяются только при получении ссылки на <xref:System.IO.IsolatedStorage.IsolatedStorage> будет получен, обычно в <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод. Защиту ссылок на <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объектов отвечает, поэтому код, использующий эти ссылки.  
  
## <a name="example"></a>Пример  
 Ниже приведен простой пример получения классом хранилища, изолированного по пользователю и сборке. Код может быть изменен для получения хранилища, изолированного по пользователю, домену и сборке, путем добавления <xref:System.IO.IsolatedStorage.IsolatedStorageScope.Domain?displayProperty=nameWithType> к аргументам, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод передает.  
  
 После выполнения кода можно убедиться, что хранилище создано, введя **StoreAdm/LIST** из командной строки. Эта процедура выполняется [средство изолированного хранилища (Storeadm.exe)](../../../docs/framework/tools/storeadm-exe-isolated-storage-tool.md) и выводит все текущие изолированные хранилища для пользователя.  
  
 [!code-cpp[Conceptual.IsolatedStorage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source6.cpp#7)]
 [!code-csharp[Conceptual.IsolatedStorage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source6.cs#7)]
 [!code-vb[Conceptual.IsolatedStorage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source6.vb#7)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageScope>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)  
 [Типы изоляции](../../../docs/standard/io/types-of-isolation.md)  
 [Сборки в среде CLR](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
