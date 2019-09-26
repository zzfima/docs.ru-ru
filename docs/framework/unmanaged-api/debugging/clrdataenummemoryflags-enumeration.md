---
title: Перечисление CLRDataEnumMemoryFlags
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67b85917be590bdba7ed3f10972ad39b731dbcdd
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274242"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="e4ba8-102">Перечисление CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="e4ba8-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="e4ba8-103">Указывает, к каким областям памяти должен быть вызван вызов метода [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4ba8-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ba8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4ba8-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e4ba8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e4ba8-105">Members</span></span>  
  
|<span data-ttu-id="e4ba8-106">Член</span><span class="sxs-lookup"><span data-stu-id="e4ba8-106">Member</span></span>|<span data-ttu-id="e4ba8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e4ba8-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="e4ba8-108">Мини-дамп, то есть дамп разреженной памяти.</span><span class="sxs-lookup"><span data-stu-id="e4ba8-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="e4ba8-109">Полный дамп кучи.</span><span class="sxs-lookup"><span data-stu-id="e4ba8-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e4ba8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e4ba8-110">Requirements</span></span>  
 <span data-ttu-id="e4ba8-111">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4ba8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ba8-112">**Заголовок.** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="e4ba8-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e4ba8-113">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="e4ba8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4ba8-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ba8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ba8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4ba8-115">See also</span></span>

- [<span data-ttu-id="e4ba8-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="e4ba8-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
