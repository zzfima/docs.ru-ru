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
ms.openlocfilehash: 4c5d4bc1fa82f7623168050f4ee36f0ea3cd171e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796441"
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="aa0b8-102">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="aa0b8-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="aa0b8-103">Служит в качестве перечислителя для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aa0b8-104">Методы</span><span class="sxs-lookup"><span data-stu-id="aa0b8-104">Methods</span></span>  
  
|<span data-ttu-id="aa0b8-105">Метод</span><span class="sxs-lookup"><span data-stu-id="aa0b8-105">Method</span></span>|<span data-ttu-id="aa0b8-106">Описание</span><span class="sxs-lookup"><span data-stu-id="aa0b8-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="aa0b8-107">Возвращает указатель интерфейса на новый `IEnumReferenceIdentity` объект, содержащий те же элементы, что и этот `IEnumReferenceIdentity`объект.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="aa0b8-108">Возвращает указанное число `IReferenceIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="aa0b8-109">Перемещает указатель инструкций в начало `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="aa0b8-110">Перемещает указатель инструкции вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="aa0b8-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa0b8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="aa0b8-111">Requirements</span></span>  
 <span data-ttu-id="aa0b8-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa0b8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa0b8-113">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="aa0b8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="aa0b8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa0b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa0b8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="aa0b8-115">See also</span></span>

- [<span data-ttu-id="aa0b8-116">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="aa0b8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="aa0b8-117">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="aa0b8-117">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
