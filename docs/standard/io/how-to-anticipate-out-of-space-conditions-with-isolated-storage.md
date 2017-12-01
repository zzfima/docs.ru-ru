---
title: "Практическое руководство. Предупреждение нехватки места при изолированном хранении"
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
- data stores, quotas
- isolated storage, quotas
- quanitity of isolated storage used
- limit on isolated storage used
- stores, quotas
- stores, out of space conditions
- data storage using isolated storage, quotas
- storing data using isolated storage, quotas
- space remaining in isolated storage
- data stores, out of space conditions
- storing data using isolated storage, out of space conditions
- quotas for isolated storage
- isolated storage, out of space conditions
- data storage using isolated storage, out of space conditions
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d813522d0aeb9bf37582c167760d44268df27039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Практическое руководство. Предупреждение нехватки места при изолированном хранении
Код, использующий изолированное хранилище ограничен [квоты](../../../docs/standard/io/isolated-storage.md#quotas) , указывающее максимальный размер ячейки данных, в котором изолированных файлов хранения и каталоги существуют. Квота определяются политикой безопасности и конфигурируется администраторами. Если максимально допустимый размер превышен при попытке записи данных, <xref:System.IO.IsolatedStorage.IsolatedStorageException> исключение, и операция завершится ошибкой. Это помогает предотвратить атаки типа "отказ в обслуживании", может вызвать отказ запросов из-за переполнения хранилища данных приложения.  
  
 Чтобы помочь определить, является ли попытка записи по этой причине <xref:System.IO.IsolatedStorage.IsolatedStorage> класс предоставляет три свойства только для чтения: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, и <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>. Эти свойства можно использовать для определения, будет ли максимально допустимый размер хранилища превышен при записи в хранилище. Имейте в виду, что изолированное хранилище может осуществляться одновременно. Таким образом можно вычислить объем хранилища, оставшиеся, дискового пространства может использовать по времени при попытке записи в хранилище. Тем не менее максимальный размер хранилища можно использовать для определения вероятности достижения ли верхний предел в доступное хранилище.  
  
 <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> Свойство зависит от свидетельство из сборки, для правильной работы. По этой причине следует получить это свойство только для <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объекты, созданные с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод. <xref:System.IO.IsolatedStorage.IsolatedStorageFile>объекты, созданные другими способами (например, объекты, которые были возвращены из <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> метод) не будет возвращать точный максимальный размер.  
  
## <a name="example"></a>Пример  
 В следующем примере получается изолированное хранилище, создается несколько файлов и извлекает <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> свойство. Оставшееся место выводится в байтах.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)  
 [Практическое руководство. Получение хранилищ для изолированного хранения](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
