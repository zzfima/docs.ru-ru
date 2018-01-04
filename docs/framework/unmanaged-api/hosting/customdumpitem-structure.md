---
title: "Структура CustomDumpItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CustomDumpItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CustomDumpItem
helpviewer_keywords: CustomDumpItem structure [.NET Framework hosting]
ms.assetid: fd9085ff-7beb-4c38-97f0-037cd8ba4f65
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47fd4e1dd3889cc7eeaa37457b47d9b2fd6dd8b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="0b74c-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="0b74c-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="0b74c-103">Описывает элемент, добавляемый в пользовательский дамп отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0b74c-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b74c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b74c-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="0b74c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0b74c-105">Members</span></span>  
  
|<span data-ttu-id="0b74c-106">Член</span><span class="sxs-lookup"><span data-stu-id="0b74c-106">Member</span></span>|<span data-ttu-id="0b74c-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b74c-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="0b74c-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) значение, указывающее тип элемента для добавления.</span><span class="sxs-lookup"><span data-stu-id="0b74c-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="0b74c-109">В настоящее время не используется.</span><span class="sxs-lookup"><span data-stu-id="0b74c-109">Not currently used.</span></span> <span data-ttu-id="0b74c-110">Все элементы, добавленные на объединения не должен превышать размер указателя.</span><span class="sxs-lookup"><span data-stu-id="0b74c-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="0b74c-111">Если `struct` — требуется, необходимо выделить его отдельно и выберите его.</span><span class="sxs-lookup"><span data-stu-id="0b74c-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b74c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b74c-112">Remarks</span></span>  
 <span data-ttu-id="0b74c-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="0b74c-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b74c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0b74c-114">Requirements</span></span>  
 <span data-ttu-id="0b74c-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b74c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b74c-116">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="0b74c-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="0b74c-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0b74c-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b74c-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b74c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b74c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0b74c-119">See Also</span></span>  
 [<span data-ttu-id="0b74c-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="0b74c-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
