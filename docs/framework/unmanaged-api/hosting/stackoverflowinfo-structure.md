---
title: "Структура StackOverflowInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StackOverflowInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: StackOverflowInfo
helpviewer_keywords: StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 102f744ecc769a10161cd20767e8e49c838252a7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="8d78d-102">Структура StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="8d78d-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="8d78d-103">Сохраняет тип произошедшего переполнения и сведения о исключение возникло из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="8d78d-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d78d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d78d-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="8d78d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8d78d-105">Members</span></span>  
  
|<span data-ttu-id="8d78d-106">Член</span><span class="sxs-lookup"><span data-stu-id="8d78d-106">Member</span></span>|<span data-ttu-id="8d78d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8d78d-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="8d78d-108">Значение [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) перечисления, указывающее тип переполнения.</span><span class="sxs-lookup"><span data-stu-id="8d78d-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="8d78d-109">Указатель на объект Win32 `EXCEPTION_POINTERS` объект, который содержит запись исключения зависит от компьютера описание исключения и записи контекста, зависимых от компьютера описание контекст процессора в момент возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="8d78d-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d78d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="8d78d-110">Remarks</span></span>  
 <span data-ttu-id="8d78d-111">Объект `StackOverflowInfo` объект передается [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод `Event_StackOverflow` события.</span><span class="sxs-lookup"><span data-stu-id="8d78d-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d78d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8d78d-112">Requirements</span></span>  
 <span data-ttu-id="8d78d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d78d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d78d-114">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="8d78d-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="8d78d-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d78d-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d78d-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d78d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d78d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8d78d-117">See Also</span></span>  
 [<span data-ttu-id="8d78d-118">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="8d78d-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
