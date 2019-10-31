---
title: Интерфейс IEnumReferenceIdentity
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
ms.openlocfilehash: 1305b9ebe3cd87ba002ee87610ff309d015a44e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131745"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="398fa-102">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="398fa-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="398fa-103">Служит перечислителем для коллекции объектов `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="398fa-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="398fa-104">Методы</span><span class="sxs-lookup"><span data-stu-id="398fa-104">Methods</span></span>  
  
|<span data-ttu-id="398fa-105">Метод</span><span class="sxs-lookup"><span data-stu-id="398fa-105">Method</span></span>|<span data-ttu-id="398fa-106">Описание</span><span class="sxs-lookup"><span data-stu-id="398fa-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="398fa-107">Возвращает указатель интерфейса на новый `IEnumReferenceIdentity`, содержащий те же элементы, что и этот `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="398fa-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="398fa-108">Возвращает указанное число объектов `IReferenceIdentity`, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="398fa-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="398fa-109">Перемещает указатель инструкции в начало этого `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="398fa-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="398fa-110">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="398fa-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="398fa-111">Требования</span><span class="sxs-lookup"><span data-stu-id="398fa-111">Requirements</span></span>  
 <span data-ttu-id="398fa-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="398fa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="398fa-113">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="398fa-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="398fa-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="398fa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398fa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="398fa-115">See also</span></span>

- [<span data-ttu-id="398fa-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="398fa-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="398fa-117">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="398fa-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
