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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1f2ea9d0e20cb67cc36d0b5883e483ce98941b2f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743222"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="1e6fd-102">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="1e6fd-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="1e6fd-103">Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e6fd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1e6fd-104">Methods</span></span>  
  
|<span data-ttu-id="1e6fd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1e6fd-105">Method</span></span>|<span data-ttu-id="1e6fd-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="1e6fd-107">Получает указатель интерфейса на новый `IEnumReferenceIdentity` , содержащий те же члены, что это `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="1e6fd-108">Возвращает заданное число `IReferenceIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="1e6fd-109">Перемещает указатель инструкций в начале `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="1e6fd-110">Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e6fd-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1e6fd-111">Requirements</span></span>  
 <span data-ttu-id="1e6fd-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e6fd-113">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1e6fd-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1e6fd-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e6fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e6fd-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1e6fd-115">See also</span></span>
- [<span data-ttu-id="1e6fd-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="1e6fd-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="1e6fd-117">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="1e6fd-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
