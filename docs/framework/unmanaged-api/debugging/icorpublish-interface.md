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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7581d68f5c2b575403ddc84d06147f012e7ab39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076345"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="f78eb-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="f78eb-102">ICorPublish Interface</span></span>
<span data-ttu-id="f78eb-103">Служит универсальным интерфейсом для публикации сведений о процессах и сведения о доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="f78eb-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f78eb-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f78eb-104">Methods</span></span>  
  
|<span data-ttu-id="f78eb-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f78eb-105">Method</span></span>|<span data-ttu-id="f78eb-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f78eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f78eb-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="f78eb-107">EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md)|<span data-ttu-id="f78eb-108">Получает [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляру, содержащему управляемых процессов, запущенных на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f78eb-108">Gets an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="f78eb-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="f78eb-109">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-getprocess-method.md)|<span data-ttu-id="f78eb-110">Получает [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) экземпляр, представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="f78eb-110">Gets an [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f78eb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f78eb-111">Requirements</span></span>  
 <span data-ttu-id="f78eb-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f78eb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f78eb-113">**Заголовок.** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f78eb-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f78eb-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f78eb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f78eb-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f78eb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f78eb-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f78eb-116">See also</span></span>

- [<span data-ttu-id="f78eb-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f78eb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f78eb-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="f78eb-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
