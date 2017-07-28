---
title: "Практическое руководство. Предупреждение нехватки места при изолированном хранении | Microsoft Docs"
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
  - "хранилища данных, квоты"
  - "изолированное хранилище, квоты"
  - "количество используемых изолированных сохранений"
  - "ограничение, накладываемое на используемое изолированное хранилище"
  - "хранилища, квоты"
  - "хранилища, условия нехватки места"
  - "хранение данных с помощью изолированного хранилища, квоты"
  - "сохранение данных с помощью изолированного хранилища, квоты"
  - "свободное место в изолированном хранилище"
  - "хранилища данных, условия нехватки места"
  - "сохранение данных с помощью изолированного хранилища, условия нехватки места"
  - "квоты для изолированного хранилища"
  - "изолированное хранилище, условия нехватки места"
  - "хранение данных с помощью изолированного хранилища, условия нехватки места"
ms.assetid: e35d4535-3732-421e-b1a3-37412e036145
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Предупреждение нехватки места при изолированном хранении
Использующий изолированное хранилище код ограничен [квотой](../../../docs/standard/io/isolated-storage.md#quotas), определяющей максимальный размер ячейки данных, в которой располагаются файлы и каталоги изолированного хранилища.  Квота определяется политикой безопасности и конфигурируется администраторами.  Если при попытке записи данных превышен максимально допустимый размер, создается исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException>, и операция завершается с ошибкой.  Это помогает предотвратить злонамеренные атаки типа "отказ в обслуживании", которые могут привести к отказу приложения от обслуживания запросов из\-за переполнения хранилища данных.  
  
 Чтобы помочь определить, завершится ли неудачей попытка записи по этой причине, класс <xref:System.IO.IsolatedStorage.IsolatedStorage> предоставляет три свойства, доступные только для чтения: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.  Можно использовать данное свойство для определения, будет ли максимально допустимый размер хранилища превышен при попытке записи.  Следует иметь в виду, что доступ к изолированному хранению может быть параллельным. Поэтому к моменту попытки записи в оставшееся хранилище в нем свободное место, которое было рассчитано таким способом, может быть уже использовано.  Однако можно использовать максимальный размер хранилища для определения, является ли верхний предел на диске достигнутым.  
  
 Свойство <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> зависит от свидетельства о надлежащей работе сборки.  По этой причине следует получить это свойство только в объектах <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, которые были созданы с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> или метода <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>.  Объекты <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, созданные любым другим способом \(например, объекты, возвращенные методом <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>\), не возвращают точный максимальный размер.  
  
## Пример  
 В следующем примере получается изолированное хранилище, создается несколько файлов и извлекается свойство <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>.  Размер оставшегося места выводится в байтах.  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## См. также  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)   
 [Практическое руководство. Получение хранилищ для изолированного хранения](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)