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
ms.openlocfilehash: 63c3ecd0ae0d9e1df62d73eb05b759093583f652
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142887"
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="d69c9-102">Перечисление NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="d69c9-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="d69c9-103">Определяет обратные вызовы для функций отладчика.</span><span class="sxs-lookup"><span data-stu-id="d69c9-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="d69c9-104">Дополнительные сведения см. в разделе [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d69c9-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d69c9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d69c9-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d69c9-106">Участники</span><span class="sxs-lookup"><span data-stu-id="d69c9-106">Members</span></span>  
  
|<span data-ttu-id="d69c9-107">Член</span><span class="sxs-lookup"><span data-stu-id="d69c9-107">Member</span></span>|<span data-ttu-id="d69c9-108">Описание</span><span class="sxs-lookup"><span data-stu-id="d69c9-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="d69c9-109">Указывает, что [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d69c9-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="d69c9-110">Указывает, что [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d69c9-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="d69c9-111">Указывает, что [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d69c9-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="d69c9-112">Указывает, что [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) должен быть вызван метод.</span><span class="sxs-lookup"><span data-stu-id="d69c9-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="d69c9-113">Указывает, что все [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) методы должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="d69c9-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="d69c9-114">Активирует все существующие и будущие уведомления.</span><span class="sxs-lookup"><span data-stu-id="d69c9-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="d69c9-115">Указывает, что методы уведомления не должны вызываться.</span><span class="sxs-lookup"><span data-stu-id="d69c9-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d69c9-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d69c9-116">Requirements</span></span>  
 <span data-ttu-id="d69c9-117">**Заголовок.** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="d69c9-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69c9-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d69c9-118">See also</span></span>

- [<span data-ttu-id="d69c9-119">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="d69c9-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
