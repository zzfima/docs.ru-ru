---
title: Интерфейс ICorPublishProcess
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 04f6a088c5bbe96e3909ba600aa8ffab937abe2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140400"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="589b1-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="589b1-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="589b1-103">Предоставляет методы, которые обращаются к сведениям, отображаемым в процессе.</span><span class="sxs-lookup"><span data-stu-id="589b1-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="589b1-104">Методы</span><span class="sxs-lookup"><span data-stu-id="589b1-104">Methods</span></span>  
  
|<span data-ttu-id="589b1-105">Метод</span><span class="sxs-lookup"><span data-stu-id="589b1-105">Method</span></span>|<span data-ttu-id="589b1-106">Описание</span><span class="sxs-lookup"><span data-stu-id="589b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="589b1-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="589b1-107">EnumAppDomains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="589b1-108">Возвращает экземпляр [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) , содержащий домены приложений в процессе, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="589b1-108">Gets an [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="589b1-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="589b1-109">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="589b1-110">Возвращает полный путь к исполняемому файлу для процесса, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="589b1-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="589b1-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="589b1-111">GetProcessID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="589b1-112">Возвращает идентификатор операционной системы для процесса, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="589b1-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="589b1-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="589b1-113">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="589b1-114">Возвращает значение, указывающее, называется ли процесс, на который ссылается эта `ICorPublishProcess`, выполнением управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="589b1-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="589b1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="589b1-115">Requirements</span></span>  
 <span data-ttu-id="589b1-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="589b1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="589b1-117">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="589b1-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="589b1-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="589b1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="589b1-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="589b1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589b1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="589b1-120">See also</span></span>

- [<span data-ttu-id="589b1-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="589b1-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="589b1-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="589b1-122">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
