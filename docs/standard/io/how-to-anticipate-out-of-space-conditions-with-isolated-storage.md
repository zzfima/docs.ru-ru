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
# <a name="how-to-anticipate-out-of-space-conditions-with-isolated-storage"></a><span data-ttu-id="9898f-102">Практическое руководство. Предупреждение нехватки места при изолированном хранении</span><span class="sxs-lookup"><span data-stu-id="9898f-102">How to: Anticipate Out-of-Space Conditions with Isolated Storage</span></span>
<span data-ttu-id="9898f-103">Код, использующий изолированное хранилище ограничен [квоты](../../../docs/standard/io/isolated-storage.md#quotas) , указывающее максимальный размер ячейки данных, в котором изолированных файлов хранения и каталоги существуют.</span><span class="sxs-lookup"><span data-stu-id="9898f-103">Code that uses isolated storage is constrained by a [quota](../../../docs/standard/io/isolated-storage.md#quotas) that specifies the maximum size for the data compartment in which isolated storage files and directories exist.</span></span> <span data-ttu-id="9898f-104">Квота определяются политикой безопасности и конфигурируется администраторами.</span><span class="sxs-lookup"><span data-stu-id="9898f-104">The quota is defined by security policy and is configurable by administrators.</span></span> <span data-ttu-id="9898f-105">Если максимально допустимый размер превышен при попытке записи данных, <xref:System.IO.IsolatedStorage.IsolatedStorageException> исключение, и операция завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="9898f-105">If the maximum allowed size is exceeded when you try to write data, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown and the operation fails.</span></span> <span data-ttu-id="9898f-106">Это помогает предотвратить атаки типа "отказ в обслуживании", может вызвать отказ запросов из-за переполнения хранилища данных приложения.</span><span class="sxs-lookup"><span data-stu-id="9898f-106">This helps prevent malicious denial-of-service attacks that could cause the application to refuse requests because data storage is filled.</span></span>  
  
 <span data-ttu-id="9898f-107">Чтобы помочь определить, является ли попытка записи по этой причине <xref:System.IO.IsolatedStorage.IsolatedStorage> класс предоставляет три свойства только для чтения: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, и <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span><span class="sxs-lookup"><span data-stu-id="9898f-107">To help you determine whether a given write attempt is likely to fail for this reason, the <xref:System.IO.IsolatedStorage.IsolatedStorage> class provides three read-only properties: <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorage.UsedSize%2A>, and <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A>.</span></span> <span data-ttu-id="9898f-108">Эти свойства можно использовать для определения, будет ли максимально допустимый размер хранилища превышен при записи в хранилище.</span><span class="sxs-lookup"><span data-stu-id="9898f-108">You can use these properties to determine whether writing to the store will cause the maximum allowed size of the store to be exceeded.</span></span> <span data-ttu-id="9898f-109">Имейте в виду, что изолированное хранилище может осуществляться одновременно. Таким образом можно вычислить объем хранилища, оставшиеся, дискового пространства может использовать по времени при попытке записи в хранилище.</span><span class="sxs-lookup"><span data-stu-id="9898f-109">Keep in mind that isolated storage can be accessed concurrently; therefore, when you compute the amount of remaining storage, the storage space could be consumed by the time you try to write to the store.</span></span> <span data-ttu-id="9898f-110">Тем не менее максимальный размер хранилища можно использовать для определения вероятности достижения ли верхний предел в доступное хранилище.</span><span class="sxs-lookup"><span data-stu-id="9898f-110">However, you can use the maximum size of the store to help determine whether the upper limit on available storage is about to be reached.</span></span>  
  
 <span data-ttu-id="9898f-111"><xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> Свойство зависит от свидетельство из сборки, для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="9898f-111">The <xref:System.IO.IsolatedStorage.IsolatedStorage.Quota%2A> property depends on evidence from the assembly to work properly.</span></span> <span data-ttu-id="9898f-112">По этой причине следует получить это свойство только для <xref:System.IO.IsolatedStorage.IsolatedStorageFile> объекты, созданные с помощью <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, или <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9898f-112">For this reason, you should retrieve this property only on <xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForAssembly%2A>, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetUserStoreForDomain%2A>, or <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetStore%2A> method.</span></span> <span data-ttu-id="9898f-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile>объекты, созданные другими способами (например, объекты, которые были возвращены из <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> метод) не будет возвращать точный максимальный размер.</span><span class="sxs-lookup"><span data-stu-id="9898f-113"><xref:System.IO.IsolatedStorage.IsolatedStorageFile> objects that were created in any other way (for example, objects that were returned from the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> method) will not return an accurate maximum size.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9898f-114">Пример</span><span class="sxs-lookup"><span data-stu-id="9898f-114">Example</span></span>  
 <span data-ttu-id="9898f-115">В следующем примере получается изолированное хранилище, создается несколько файлов и извлекает <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9898f-115">The following code example obtains an isolated store, creates a few files, and retrieves the <xref:System.IO.IsolatedStorage.IsolatedStorage.AvailableFreeSpace%2A> property.</span></span> <span data-ttu-id="9898f-116">Оставшееся место выводится в байтах.</span><span class="sxs-lookup"><span data-stu-id="9898f-116">The remaining space is reported in bytes.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#8](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source7.cpp#8)]
 [!code-csharp[Conceptual.IsolatedStorage#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source7.cs#8)]
 [!code-vb[Conceptual.IsolatedStorage#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source7.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="9898f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="9898f-117">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="9898f-118">Изолированное хранилище</span><span class="sxs-lookup"><span data-stu-id="9898f-118">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)  
 [<span data-ttu-id="9898f-119">Практическое руководство. Получение хранилищ для изолированного хранения</span><span class="sxs-lookup"><span data-stu-id="9898f-119">How to: Obtain Stores for Isolated Storage</span></span>](../../../docs/standard/io/how-to-obtain-stores-for-isolated-storage.md)
