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
ms.openlocfilehash: 80ea3afef4aee51760e3a2ce6a2b895bca4a6ec5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224073"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="b789e-102">Перечисление CLRDataEnumMemoryFlags</span><span class="sxs-lookup"><span data-stu-id="b789e-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="b789e-103">Указывает области памяти вызов [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) должен включать метод.</span><span class="sxs-lookup"><span data-stu-id="b789e-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b789e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b789e-104">Syntax</span></span>  
  
```  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b789e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b789e-105">Members</span></span>  
  
|<span data-ttu-id="b789e-106">Член</span><span class="sxs-lookup"><span data-stu-id="b789e-106">Member</span></span>|<span data-ttu-id="b789e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b789e-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="b789e-108">Минидамп, дамп разреженной памяти.</span><span class="sxs-lookup"><span data-stu-id="b789e-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="b789e-109">Дамп полной кучи.</span><span class="sxs-lookup"><span data-stu-id="b789e-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b789e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b789e-110">Requirements</span></span>  
 <span data-ttu-id="b789e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b789e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b789e-112">**Заголовок.** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b789e-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b789e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b789e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b789e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b789e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b789e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b789e-115">See also</span></span>

- [<span data-ttu-id="b789e-116">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b789e-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
