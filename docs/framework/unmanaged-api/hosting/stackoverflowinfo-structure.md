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
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105911"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="f563a-102">Структура StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="f563a-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="f563a-103">Хранит тип произошедшего переполнения и сведения об исключении, порождаемом из-за переполнения.</span><span class="sxs-lookup"><span data-stu-id="f563a-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f563a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f563a-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f563a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f563a-105">Members</span></span>  
  
|<span data-ttu-id="f563a-106">Член</span><span class="sxs-lookup"><span data-stu-id="f563a-106">Member</span></span>|<span data-ttu-id="f563a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f563a-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="f563a-108">Значение перечисления [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) , указывающее тип переполнения.</span><span class="sxs-lookup"><span data-stu-id="f563a-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="f563a-109">Указатель на объект Win32 `EXCEPTION_POINTERS`, который содержит запись исключения с независимым от компьютера описанием исключения и записью контекста с зависящим от компьютера описанием контекста процессора на момент возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="f563a-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f563a-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="f563a-110">Remarks</span></span>  
 <span data-ttu-id="f563a-111">Объект `StackOverflowInfo` передается в метод [иактиононклревент:: oneven](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) для событий `Event_StackOverflow`.</span><span class="sxs-lookup"><span data-stu-id="f563a-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f563a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f563a-112">Requirements</span></span>  
 <span data-ttu-id="f563a-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f563a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f563a-114">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="f563a-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f563a-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f563a-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f563a-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f563a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f563a-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f563a-117">See also</span></span>

- [<span data-ttu-id="f563a-118">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="f563a-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
