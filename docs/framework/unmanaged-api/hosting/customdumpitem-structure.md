---
title: Структура CustomDumpItem
ms.date: 03/30/2017
api_name:
- CustomDumpItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CustomDumpItem
helpviewer_keywords:
- CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type:
- apiref
ms.openlocfilehash: 154beef9398029f31dcb4d081019b9f292238af4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176478"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="fe588-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="fe588-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="fe588-103">Описывает элемент, который должен быть добавлен в пользовательский дамп в сообщении об ошибке.</span><span class="sxs-lookup"><span data-stu-id="fe588-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe588-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe588-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="fe588-105">Члены</span><span class="sxs-lookup"><span data-stu-id="fe588-105">Members</span></span>  
  
|<span data-ttu-id="fe588-106">Участник</span><span class="sxs-lookup"><span data-stu-id="fe588-106">Member</span></span>|<span data-ttu-id="fe588-107">Описание</span><span class="sxs-lookup"><span data-stu-id="fe588-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="fe588-108">Значение [ECustomDumpItemKind,](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) которое указывает вид товара, который будет добавлен.</span><span class="sxs-lookup"><span data-stu-id="fe588-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="fe588-109">В настоящий момент не используется.</span><span class="sxs-lookup"><span data-stu-id="fe588-109">Not currently used.</span></span> <span data-ttu-id="fe588-110">Любые элементы, добавленные в союз, должны быть не больше размера указателя.</span><span class="sxs-lookup"><span data-stu-id="fe588-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="fe588-111">Если `struct` требуется, вы должны выделить его отдельно и указать на него.</span><span class="sxs-lookup"><span data-stu-id="fe588-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fe588-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="fe588-112">Remarks</span></span>  
 <span data-ttu-id="fe588-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр `CustomDumpItem`типа .</span><span class="sxs-lookup"><span data-stu-id="fe588-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe588-114">Требования</span><span class="sxs-lookup"><span data-stu-id="fe588-114">Requirements</span></span>  
 <span data-ttu-id="fe588-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe588-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe588-116">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="fe588-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="fe588-117">**Библиотека:** Включено в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe588-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe588-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe588-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe588-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fe588-119">See also</span></span>

- [<span data-ttu-id="fe588-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="fe588-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
