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
ms.openlocfilehash: ae64edd8a3a628100d4c51d0b78be1bc8d49fc17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138284"
---
# <a name="customdumpitem-structure"></a><span data-ttu-id="d4c44-102">Структура CustomDumpItem</span><span class="sxs-lookup"><span data-stu-id="d4c44-102">CustomDumpItem Structure</span></span>
<span data-ttu-id="d4c44-103">Описывает элемент, добавляемый в пользовательский дамп в отчетах об ошибках.</span><span class="sxs-lookup"><span data-stu-id="d4c44-103">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4c44-104">Syntax</span></span>  
  
```cpp  
struct {  
    ECustomDumpItemKind itemKind;   
    union {  
        UINT_PTR pReserved;  
    }  
} CustomDumpItem;  
```  
  
## <a name="members"></a><span data-ttu-id="d4c44-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d4c44-105">Members</span></span>  
  
|<span data-ttu-id="d4c44-106">Член</span><span class="sxs-lookup"><span data-stu-id="d4c44-106">Member</span></span>|<span data-ttu-id="d4c44-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d4c44-107">Description</span></span>|  
|------------|-----------------|  
|`itemKind`|<span data-ttu-id="d4c44-108">Значение [екустомдумпитемкинд](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) , указывающее тип добавляемого элемента.</span><span class="sxs-lookup"><span data-stu-id="d4c44-108">An [ECustomDumpItemKind](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md) value that indicates the kind of item to be added.</span></span>|  
|`pReserved`|<span data-ttu-id="d4c44-109">В настоящее время не используется.</span><span class="sxs-lookup"><span data-stu-id="d4c44-109">Not currently used.</span></span> <span data-ttu-id="d4c44-110">Все элементы, добавляемые в объединение, не должны быть больше размера указателя.</span><span class="sxs-lookup"><span data-stu-id="d4c44-110">Any items added to the union must be no larger than pointer size.</span></span> <span data-ttu-id="d4c44-111">Если требуется `struct`, необходимо выделить его отдельно и указать на него.</span><span class="sxs-lookup"><span data-stu-id="d4c44-111">If a `struct` is required, you must allocate it separately and point to it.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4c44-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="d4c44-112">Remarks</span></span>  
 <span data-ttu-id="d4c44-113">[Iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) принимает параметр типа `CustomDumpItem`.</span><span class="sxs-lookup"><span data-stu-id="d4c44-113">[ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) takes a parameter of type `CustomDumpItem`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c44-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d4c44-114">Requirements</span></span>  
 <span data-ttu-id="d4c44-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4c44-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4c44-116">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="d4c44-116">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d4c44-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d4c44-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4c44-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c44-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c44-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d4c44-119">See also</span></span>

- [<span data-ttu-id="d4c44-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="d4c44-120">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
