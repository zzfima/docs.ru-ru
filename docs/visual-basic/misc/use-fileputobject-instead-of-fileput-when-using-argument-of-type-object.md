---
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: bf1f50d0d8eb9b0b8518075b0e48f40645a02a25
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913212"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="4d6a9-102">При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut</span><span class="sxs-lookup"><span data-stu-id="4d6a9-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="4d6a9-103">Метод `FilePut` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="4d6a9-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="4d6a9-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4d6a9-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4d6a9-105">To correct this error</span></span>  
  
- <span data-ttu-id="4d6a9-106">Замените `FilePut` объектом `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="4d6a9-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="4d6a9-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="4d6a9-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="4d6a9-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6a9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="4d6a9-109">See also</span></span>

- [<span data-ttu-id="4d6a9-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="4d6a9-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="4d6a9-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="4d6a9-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
