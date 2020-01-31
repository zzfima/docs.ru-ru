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
ms.openlocfilehash: 61cac0922423acabef3d47618d98ddf082d071da
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790674"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="4c384-102">Интерфейс ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="4c384-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="4c384-103">Подкласс интерфейса [ICorPublishEnum](icorpublishenum-interface.md) , предоставляющий методы для прохода по коллекции объектов [ICorPublishAppDomain](icorpublishappdomain-interface.md) , которые в данный момент существуют в процессе.</span><span class="sxs-lookup"><span data-stu-id="4c384-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c384-104">Методы</span><span class="sxs-lookup"><span data-stu-id="4c384-104">Methods</span></span>  
  
|<span data-ttu-id="4c384-105">Метод</span><span class="sxs-lookup"><span data-stu-id="4c384-105">Method</span></span>|<span data-ttu-id="4c384-106">Описание</span><span class="sxs-lookup"><span data-stu-id="4c384-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c384-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="4c384-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="4c384-108">Возвращает указанное число экземпляров `ICorPublishAppDomain` из коллекции, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="4c384-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c384-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="4c384-109">Remarks</span></span>  
 <span data-ttu-id="4c384-110">Интерфейс `ICorPublishAppDomainEnum` реализует методы абстрактного интерфейса [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="4c384-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c384-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4c384-111">Requirements</span></span>  
 <span data-ttu-id="4c384-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c384-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c384-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="4c384-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4c384-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c384-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c384-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c384-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c384-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="4c384-116">See also</span></span>

- [<span data-ttu-id="4c384-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4c384-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4c384-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="4c384-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
