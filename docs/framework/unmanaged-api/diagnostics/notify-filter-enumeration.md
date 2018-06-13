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
ms.openlocfilehash: 98c3e1ed3da209cbded5d76d938d2420fce606be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431023"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="cc0e2-102">Перечисление NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="cc0e2-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="cc0e2-103">Определяет обратные вызовы для функций отладчика.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="cc0e2-104">Дополнительные сведения см. в разделе [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc0e2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc0e2-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="cc0e2-106">Участники</span><span class="sxs-lookup"><span data-stu-id="cc0e2-106">Members</span></span>  
  
|<span data-ttu-id="cc0e2-107">Член</span><span class="sxs-lookup"><span data-stu-id="cc0e2-107">Member</span></span>|<span data-ttu-id="cc0e2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="cc0e2-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="cc0e2-109">Указывает, что [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) следует вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="cc0e2-110">Указывает, что [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) следует вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="cc0e2-111">Указывает, что [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) следует вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="cc0e2-112">Указывает, что [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) следует вызвать метод.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="cc0e2-113">Указывает, что все [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) методы должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="cc0e2-114">Активирует все существующие и будущие уведомления.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="cc0e2-115">Указывает, что следует вызвать методы без уведомления.</span><span class="sxs-lookup"><span data-stu-id="cc0e2-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc0e2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cc0e2-116">Requirements</span></span>  
 <span data-ttu-id="cc0e2-117">**Заголовок:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="cc0e2-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc0e2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="cc0e2-118">See Also</span></span>  
 [<span data-ttu-id="cc0e2-119">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="cc0e2-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
