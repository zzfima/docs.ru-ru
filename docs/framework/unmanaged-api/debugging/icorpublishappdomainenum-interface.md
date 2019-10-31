---
title: Интерфейс ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: cbe2aa48a8b67b0b6e88f7b5267bc70848fe3cec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140323"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="b060b-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="b060b-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="b060b-103">Подкласс интерфейса [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="b060b-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b060b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b060b-104">Methods</span></span>  
  
|<span data-ttu-id="b060b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b060b-105">Method</span></span>|<span data-ttu-id="b060b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b060b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b060b-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="b060b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="b060b-108">Возвращает указанное число экземпляров `ICorPublishAppDomain` из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="b060b-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b060b-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="b060b-109">Remarks</span></span>  
 <span data-ttu-id="b060b-110">Интерфейс `ICorPublishAppDomainEnum` реализует методы абстрактного интерфейса [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b060b-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b060b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b060b-111">Requirements</span></span>  
 <span data-ttu-id="b060b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b060b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b060b-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="b060b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b060b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b060b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b060b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b060b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b060b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b060b-116">See also</span></span>

- [<span data-ttu-id="b060b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b060b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b060b-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="b060b-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
