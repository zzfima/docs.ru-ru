---
title: Перечисление COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 40efe81f72a2043503bf521e3e47dad1a7f4530c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448451"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="c1d1d-102">Перечисление COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="c1d1d-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="c1d1d-103">Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="c1d1d-104">Эти значения можно комбинировать с помощью побитовой операции OR, чтобы указать, что поле имеет несколько различных статических качеств.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d1d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1d1d-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="c1d1d-106">Члены</span><span class="sxs-lookup"><span data-stu-id="c1d1d-106">Members</span></span>  
  
|<span data-ttu-id="c1d1d-107">Член</span><span class="sxs-lookup"><span data-stu-id="c1d1d-107">Member</span></span>|<span data-ttu-id="c1d1d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="c1d1d-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="c1d1d-109">Поле не является статическим.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="c1d1d-110">Поле является статическим в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="c1d1d-111">Поле является статическим для потока.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="c1d1d-112">Поле является статическим по контексту.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="c1d1d-113">Поле является относительным виртуальным адресом (RVA) — статическим.</span><span class="sxs-lookup"><span data-stu-id="c1d1d-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c1d1d-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c1d1d-114">Requirements</span></span>  
 <span data-ttu-id="c1d1d-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1d1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d1d-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1d1d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1d1d-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1d1d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d1d-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d1d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c1d1d-119">See also</span></span>

- [<span data-ttu-id="c1d1d-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="c1d1d-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
