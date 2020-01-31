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
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790728"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="8877b-102">Интерфейс ICorPublish</span><span class="sxs-lookup"><span data-stu-id="8877b-102">ICorPublish Interface</span></span>
<span data-ttu-id="8877b-103">Служит общим интерфейсом для публикации сведений о процессах и сведениях о доменах приложений в этих процессах.</span><span class="sxs-lookup"><span data-stu-id="8877b-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8877b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8877b-104">Methods</span></span>  
  
|<span data-ttu-id="8877b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8877b-105">Method</span></span>|<span data-ttu-id="8877b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8877b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8877b-107">Метод EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="8877b-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="8877b-108">Возвращает экземпляр [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) , содержащий управляемые процессы, запущенные на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="8877b-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="8877b-109">Метод GetProcess</span><span class="sxs-lookup"><span data-stu-id="8877b-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="8877b-110">Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.</span><span class="sxs-lookup"><span data-stu-id="8877b-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8877b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8877b-111">Requirements</span></span>  
 <span data-ttu-id="8877b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8877b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8877b-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="8877b-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8877b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8877b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8877b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8877b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8877b-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="8877b-116">See also</span></span>

- [<span data-ttu-id="8877b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8877b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8877b-118">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="8877b-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
