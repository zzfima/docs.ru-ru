---
title: Практическое руководство. Предупреждение нехватки места при изолированном хранении
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data stores, quotas
- isolated storage, quotas
- quantity of isolated storage used
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
ms.openlocfilehash: 5666019e1a65880221261ef5ad704f82c37263b2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708119"
---
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a>Практическое руководство. Предупреждение нехватки места при изолированном хранении

Код, использующий изолированное хранилище, ограничен [квотой](../../../docs/standard/io/isolated-storage.md#quotas) на максимальный размер секции данных, в которой существуют изолированные файлы и каталоги хранения. Эта квота определяется политикой безопасности и настраивается администраторами. Если при попытке записи данных превышается максимальный размер, создается исключение <xref:System.IO.IsolatedStorage.IsolatedStorageException> и операция завершается ошибкой. Это помогает предотвратить атаки типа "отказ в обслуживании", которые могут привести к неспособности приложения обрабатывать запросы из-за переполнения хранилища данных.

Чтобы заранее определить, может ли попытка записи привести к сбою по этой причине, класс <xref:System.IO.IsolatedStorage.IsolatedStorage> предоставляет три свойства <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A> и <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>, доступных только для чтения. С их помощью вы можете оценить, будет ли превышен максимальный размер при записи в хранилище. Имейте в виду, что к изолированному хранилищу можно обращаться параллельно. Это означает, что доступное пространство хранилища может измениться в период между проверкой свободного места и попыткой записи в хранилище. Но максимальный размер операции всегда полезен для того, чтобы выявить приближение к лимиту доступного пространства в хранилище.

Правильность работы свойства <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> зависит от свидетельства из сборки. Поэтому это свойство следует использовать только для объектов <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, созданных с помощью методов <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A> или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A>. Объекты <xref:System.IO.IsolatedStorage.IsolatedStorageFile>, созданные другими способами (например, возвращаемые методом <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>), не возвращают точный максимальный размер.

## <a name="example"></a>Пример

Приведенный ниже пример кода получает изолированное хранилище, создает в нем несколько файлов и извлекает свойство <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>. Это свойство возвращает остаток свободного места в байтах.

[!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
[!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
[!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]

## <a name="see-also"></a>См. также раздел

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Изолированное хранилище](../../../docs/standard/io/isolated-storage.md)
- [Практическое руководство. Получение хранилищ для изолированного хранения](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
