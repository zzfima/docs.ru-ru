---
title: "Практическое руководство. Перечисление хранилищ для изолированного хранилища"
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
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Практическое руководство. Перечисление хранилищ для изолированного хранилища
Перечислить все изолированные хранилища для текущего пользователя можно с помощью статического метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType>. Этот метод принимает значение <xref:System.IO.IsolatedStorage.IsolatedStorageScope> и возвращает перечислитель <xref:System.IO.IsolatedStorage.IsolatedStorageFile>. Перечисление хранилищ, должен иметь <xref:System.Security.Permissions.IsolatedStorageFilePermission> разрешение, которое указывает <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> значение. При вызове метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> метод с <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> значение, он возвращает массив <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объекты, определенные для текущего пользователя.  
  
## <a name="example"></a>Пример  
 В следующем примере кода извлекается хранилища, изолированного по пользователю и сборке, создается несколько файлов и эти файлы извлекаются с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> метод.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
