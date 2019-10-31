---
title: Интерфейс ICorPublish
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: 70cf2d76c7c5d1c3431506685f8506e44ab9ec4a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121770"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="67067-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="67067-102">ICorPublish Interface</span></span>
<span data-ttu-id="67067-103">Служит общим интерфейсом для публикации сведений о процессах и сведениях о доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="67067-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67067-104">Методы</span><span class="sxs-lookup"><span data-stu-id="67067-104">Methods</span></span>  
  
|<span data-ttu-id="67067-105">Метод</span><span class="sxs-lookup"><span data-stu-id="67067-105">Method</span></span>|<span data-ttu-id="67067-106">Описание</span><span class="sxs-lookup"><span data-stu-id="67067-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67067-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="67067-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="67067-108">Возвращает экземпляр [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) , содержащий управляемые процессы, запущенные на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="67067-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="67067-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="67067-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="67067-110">Возвращает экземпляр [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="67067-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="67067-111">Требования</span><span class="sxs-lookup"><span data-stu-id="67067-111">Requirements</span></span>  
 <span data-ttu-id="67067-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67067-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67067-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="67067-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="67067-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67067-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67067-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67067-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67067-116">См. также</span><span class="sxs-lookup"><span data-stu-id="67067-116">See also</span></span>

- [<span data-ttu-id="67067-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67067-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="67067-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="67067-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
