---
title: Структура StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac0f5d522a24394369583692f8c564254529bf13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137355"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="04ee2-102">Структура StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="04ee2-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="04ee2-103">Сохраняет тип произошедшего переполнения и сведения на исключение, вызванное исключение из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="04ee2-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ee2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04ee2-104">Syntax</span></span>  
  
```  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="04ee2-105">Участники</span><span class="sxs-lookup"><span data-stu-id="04ee2-105">Members</span></span>  
  
|<span data-ttu-id="04ee2-106">Член</span><span class="sxs-lookup"><span data-stu-id="04ee2-106">Member</span></span>|<span data-ttu-id="04ee2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="04ee2-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="04ee2-108">Значение [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) перечисление, указывающее тип переполнения.</span><span class="sxs-lookup"><span data-stu-id="04ee2-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="04ee2-109">Указатель на Win32 `EXCEPTION_POINTERS` объект, который содержит запись исключения зависит от компьютера описание исключения и записи контекста, зависимых от компьютера описание контекст процессора в момент возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="04ee2-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04ee2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="04ee2-110">Remarks</span></span>  
 <span data-ttu-id="04ee2-111">Объект `StackOverflowInfo` объект передается [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод `Event_StackOverflow` события.</span><span class="sxs-lookup"><span data-stu-id="04ee2-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ee2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="04ee2-112">Requirements</span></span>  
 <span data-ttu-id="04ee2-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ee2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ee2-114">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="04ee2-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="04ee2-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04ee2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04ee2-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ee2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ee2-117">См. также</span><span class="sxs-lookup"><span data-stu-id="04ee2-117">See also</span></span>

- [<span data-ttu-id="04ee2-118">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="04ee2-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
