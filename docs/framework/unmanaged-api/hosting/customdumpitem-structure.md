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
ms.openlocfilehash: 547204385b20d5b7e64bda9ea0a9e790f2ba3471
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="aceed-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="aceed-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="aceed-103">Описывает элемент, добавляемый в пользовательский дамп отчеты об ошибках.</span><span class="sxs-lookup"><span data-stu-id="aceed-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aceed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aceed-104">Syntax</span></span>  
  
```  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="aceed-105">Члены</span><span class="sxs-lookup"><span data-stu-id="aceed-105">Members</span></span>  
  
|<span data-ttu-id="aceed-106">Член</span><span class="sxs-lookup"><span data-stu-id="aceed-106">Member</span></span>|<span data-ttu-id="aceed-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aceed-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="aceed-108">[ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) значение, указывающее тип элемента для добавления.</span><span class="sxs-lookup"><span data-stu-id="aceed-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="aceed-109">В настоящее время не используется.</span><span class="sxs-lookup"><span data-stu-id="aceed-109">Not currently used.</span></span> <span data-ttu-id="aceed-110">Все элементы, добавленные на объединения не должен превышать размер указателя.</span><span class="sxs-lookup"><span data-stu-id="aceed-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="aceed-111">Если `struct` — требуется, необходимо выделить его отдельно и выберите его.</span><span class="sxs-lookup"><span data-stu-id="aceed-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aceed-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="aceed-112">Remarks</span></span>  
 <span data-ttu-id="aceed-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="aceed-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aceed-114">Требования</span><span class="sxs-lookup"><span data-stu-id="aceed-114">Requirements</span></span>  
 <span data-ttu-id="aceed-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aceed-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aceed-116">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="aceed-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="aceed-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aceed-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aceed-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aceed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aceed-119">См. также</span><span class="sxs-lookup"><span data-stu-id="aceed-119">See Also</span></span>  
 [<span data-ttu-id="aceed-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="aceed-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
