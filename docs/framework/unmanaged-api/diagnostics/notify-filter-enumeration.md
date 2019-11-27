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
ms.openlocfilehash: 92e40dbe8892d48dba1c54d9cd16faa409440b24
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438116"
---
# <a name="notify_filter-enumeration"></a><span data-ttu-id="fff50-102">Перечисление NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="fff50-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="fff50-103">Определяет обратные вызовы для функций отладчика.</span><span class="sxs-lookup"><span data-stu-id="fff50-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="fff50-104">Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fff50-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fff50-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="fff50-106">Члены</span><span class="sxs-lookup"><span data-stu-id="fff50-106">Members</span></span>  
  
|<span data-ttu-id="fff50-107">Член</span><span class="sxs-lookup"><span data-stu-id="fff50-107">Member</span></span>|<span data-ttu-id="fff50-108">Описание</span><span class="sxs-lookup"><span data-stu-id="fff50-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="fff50-109">Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="fff50-110">Указывает, что должен быть вызван метод [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="fff50-111">Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллексит](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="fff50-112">Указывает, что должен быть вызван метод [INotifySink2:: онсинккаллретурн](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="fff50-113">Указывает, что должны быть вызваны все методы [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fff50-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="fff50-114">Активирует все существующие и будущие уведомления.</span><span class="sxs-lookup"><span data-stu-id="fff50-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="fff50-115">Указывает, что методы уведомления вызывать не нужно.</span><span class="sxs-lookup"><span data-stu-id="fff50-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fff50-116">Требования</span><span class="sxs-lookup"><span data-stu-id="fff50-116">Requirements</span></span>  
 <span data-ttu-id="fff50-117">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="fff50-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fff50-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="fff50-118">See also</span></span>

- [<span data-ttu-id="fff50-119">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="fff50-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
