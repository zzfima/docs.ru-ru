---
title: При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725562"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="41ac7-102">При использовании аргумента с типом Object применяйте FilePutObject вместо FilePut</span><span class="sxs-lookup"><span data-stu-id="41ac7-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="41ac7-103">Метод `FilePut` включает аргумент типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="41ac7-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="41ac7-104">Чтобы избежать неоднозначности, следует использовать`FilePutObject` вместо `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="41ac7-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41ac7-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="41ac7-105">To correct this error</span></span>  
  
-   <span data-ttu-id="41ac7-106">Замените `FilePut` объектом `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="41ac7-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="41ac7-107">Приведите аргумент `Object` к более конкретному типу.</span><span class="sxs-lookup"><span data-stu-id="41ac7-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="41ac7-108">Используйте функциональность объекта `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="41ac7-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41ac7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="41ac7-109">See also</span></span>

- [<span data-ttu-id="41ac7-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="41ac7-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="41ac7-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="41ac7-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
