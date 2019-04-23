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
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59123491"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="2225d-102">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="2225d-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="2225d-103">Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="2225d-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2225d-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2225d-104">Methods</span></span>  
  
|<span data-ttu-id="2225d-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2225d-105">Method</span></span>|<span data-ttu-id="2225d-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2225d-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="2225d-107">Получает указатель интерфейса на новый `IEnumReferenceIdentity` , содержащий те же члены, что это `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2225d-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="2225d-108">Возвращает заданное число `IReferenceIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2225d-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="2225d-109">Перемещает указатель инструкций в начале `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="2225d-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="2225d-110">Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2225d-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2225d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="2225d-111">Requirements</span></span>  
 <span data-ttu-id="2225d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2225d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2225d-113">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="2225d-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="2225d-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2225d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2225d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2225d-115">See also</span></span>

- [<span data-ttu-id="2225d-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="2225d-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="2225d-117">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="2225d-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
