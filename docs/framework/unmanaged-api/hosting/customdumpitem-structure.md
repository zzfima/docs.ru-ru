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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 930d56fcfe7cf0d2a128c2068e724b85a224b3fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568924"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="d0cc4-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="d0cc4-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="d0cc4-103">Описывает элемент, добавляемый в пользовательский дамп отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0cc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0cc4-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="d0cc4-105">Участники</span><span class="sxs-lookup"><span data-stu-id="d0cc4-105">Members</span></span>  
  
|<span data-ttu-id="d0cc4-106">Член</span><span class="sxs-lookup"><span data-stu-id="d0cc4-106">Member</span></span>|<span data-ttu-id="d0cc4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d0cc4-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="d0cc4-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) значение, указывающее тип для добавляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="d0cc4-109">В настоящее время не используется.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-109">Not currently used.</span></span> <span data-ttu-id="d0cc4-110">Все элементы, добавляемые к объединению не должен превышать размер указателя.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="d0cc4-111">Если `struct` — требуется, необходимо выделить его отдельно и указать его.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0cc4-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0cc4-112">Remarks</span></span>  
 <span data-ttu-id="d0cc4-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="d0cc4-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0cc4-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d0cc4-114">Requirements</span></span>  
 <span data-ttu-id="d0cc4-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0cc4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0cc4-116">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="d0cc4-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d0cc4-117">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d0cc4-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0cc4-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0cc4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0cc4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d0cc4-119">See also</span></span>
- [<span data-ttu-id="d0cc4-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="d0cc4-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
