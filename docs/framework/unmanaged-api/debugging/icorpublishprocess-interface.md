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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790540"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="ffa0c-102">Интерфейс ICorPublishProcess</span><span class="sxs-lookup"><span data-stu-id="ffa0c-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="ffa0c-103">Предоставляет методы, которые обращаются к сведениям, отображаемым в процессе.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ffa0c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ffa0c-104">Methods</span></span>  
  
|<span data-ttu-id="ffa0c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ffa0c-105">Method</span></span>|<span data-ttu-id="ffa0c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ffa0c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ffa0c-107">Метод EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="ffa0c-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="ffa0c-108">Возвращает экземпляр [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) , содержащий домены приложений в процессе, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="ffa0c-109">Метод GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="ffa0c-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="ffa0c-110">Возвращает полный путь к исполняемому файлу для процесса, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="ffa0c-111">Метод GetProcessID</span><span class="sxs-lookup"><span data-stu-id="ffa0c-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="ffa0c-112">Возвращает идентификатор операционной системы для процесса, на который ссылается эта `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="ffa0c-113">Метод IsManaged</span><span class="sxs-lookup"><span data-stu-id="ffa0c-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="ffa0c-114">Возвращает значение, указывающее, называется ли процесс, на который ссылается эта `ICorPublishProcess`, выполнением управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="ffa0c-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffa0c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ffa0c-115">Requirements</span></span>  
 <span data-ttu-id="ffa0c-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffa0c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffa0c-117">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="ffa0c-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ffa0c-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffa0c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffa0c-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffa0c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffa0c-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="ffa0c-120">See also</span></span>

- [<span data-ttu-id="ffa0c-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ffa0c-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ffa0c-122">Кокласс CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="ffa0c-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
