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
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132413"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="1c115-102">Перечисление CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="1c115-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="1c115-103">Указывает, к каким областям памяти должен быть вызван вызов метода [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c115-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c115-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c115-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1c115-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1c115-105">Members</span></span>  
  
|<span data-ttu-id="1c115-106">Член</span><span class="sxs-lookup"><span data-stu-id="1c115-106">Member</span></span>|<span data-ttu-id="1c115-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1c115-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="1c115-108">Мини-дамп, то есть дамп разреженной памяти.</span><span class="sxs-lookup"><span data-stu-id="1c115-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="1c115-109">Полный дамп кучи.</span><span class="sxs-lookup"><span data-stu-id="1c115-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c115-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1c115-110">Requirements</span></span>  
 <span data-ttu-id="1c115-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c115-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c115-112">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="1c115-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1c115-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c115-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c115-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c115-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c115-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1c115-115">See also</span></span>

- [<span data-ttu-id="1c115-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="1c115-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
