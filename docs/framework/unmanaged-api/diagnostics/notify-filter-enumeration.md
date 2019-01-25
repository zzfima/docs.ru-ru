---
title: Перечисление NOTIFY_FILTER
ms.date: 03/30/2017
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fcd1d7fb1fdcd8b1ad1abf159a7828e51be392a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735770"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="d935f-102">Перечисление NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="d935f-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="d935f-103">Определяет обратные вызовы для функций отладчика.</span><span class="sxs-lookup"><span data-stu-id="d935f-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="d935f-104">Дополнительные сведения см. в разделе [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d935f-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d935f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d935f-105">Syntax</span></span>  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="d935f-106">Участники</span><span class="sxs-lookup"><span data-stu-id="d935f-106">Members</span></span>  
  
|<span data-ttu-id="d935f-107">Член</span><span class="sxs-lookup"><span data-stu-id="d935f-107">Member</span></span>|<span data-ttu-id="d935f-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="d935f-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="d935f-109">Указывает, что [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d935f-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="d935f-110">Указывает, что [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d935f-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="d935f-111">Указывает, что [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d935f-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="d935f-112">Указывает, что [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d935f-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="d935f-113">Указывает, что все [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) методы должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="d935f-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="d935f-114">Активирует все существующие и будущие уведомления.</span><span class="sxs-lookup"><span data-stu-id="d935f-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="d935f-115">Указывает, что методы уведомления не должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="d935f-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d935f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d935f-116">Requirements</span></span>  
 <span data-ttu-id="d935f-117">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d935f-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d935f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d935f-118">See also</span></span>
- [<span data-ttu-id="d935f-119">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d935f-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
