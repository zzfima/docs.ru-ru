---
title: "Интерфейс IEnumReferenceIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumReferenceIdentity
helpviewer_keywords: IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 49e1425e8e7e3d09dc36915916b887d2887dccff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ienumreferenceidentity-interface"></a><span data-ttu-id="4ea67-102">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="4ea67-102">IEnumReferenceIdentity Interface</span></span>
<span data-ttu-id="4ea67-103">Служит в качестве перечислитель для коллекции `IReferenceIdentity` объектов.</span><span class="sxs-lookup"><span data-stu-id="4ea67-103">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4ea67-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4ea67-104">Methods</span></span>  
  
|<span data-ttu-id="4ea67-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4ea67-105">Method</span></span>|<span data-ttu-id="4ea67-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4ea67-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|<span data-ttu-id="4ea67-107">Получает указатель интерфейса на новый `IEnumReferenceIdentity` , содержащий те же элементы, как это `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4ea67-107">Gets an interface pointer to a new `IEnumReferenceIdentity` that contains the same members as this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Next`|<span data-ttu-id="4ea67-108">Возвращает заданное число `IReferenceIdentity` объектов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4ea67-108">Gets the specified number of `IReferenceIdentity` objects, starting at the current position.</span></span>|  
|`IEnumReferenceIdentity::Reset`|<span data-ttu-id="4ea67-109">Перемещает указатель на начало `IEnumReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="4ea67-109">Moves the instruction pointer to the beginning of this `IEnumReferenceIdentity`.</span></span>|  
|`IEnumReferenceIdentity::Skip`|<span data-ttu-id="4ea67-110">Перемещает указатель инструкций вперед на указанное число элементов, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4ea67-110">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ea67-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4ea67-111">Requirements</span></span>  
 <span data-ttu-id="4ea67-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ea67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ea67-113">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="4ea67-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4ea67-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ea67-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4ea67-115">See Also</span></span>  
 [<span data-ttu-id="4ea67-116">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="4ea67-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="4ea67-117">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="4ea67-117">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
