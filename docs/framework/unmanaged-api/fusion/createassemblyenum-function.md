---
title: Функция CreateAssemblyEnum
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795389"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="81ec9-102">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="81ec9-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="81ec9-103">Возвращает указатель на экземпляр [IAssemblyEnum](iassemblyenum-interface.md) , который может перечислить объекты в сборке с указанным [IAssemblyName](iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="81ec9-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81ec9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81ec9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="81ec9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81ec9-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="81ec9-106">заполняет Указатель на место в памяти, содержащее запрошенный `IAssemblyEnum` указатель.</span><span class="sxs-lookup"><span data-stu-id="81ec9-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="81ec9-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="81ec9-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="81ec9-108">`pUnkReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="81ec9-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="81ec9-109">окне Объект `IAssemblyName` запрошенной сборки.</span><span class="sxs-lookup"><span data-stu-id="81ec9-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="81ec9-110">Это имя используется для фильтрации перечисления.</span><span class="sxs-lookup"><span data-stu-id="81ec9-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="81ec9-111">Для перечисления всех сборок в глобальном кэше сборок может быть задано значение null.</span><span class="sxs-lookup"><span data-stu-id="81ec9-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="81ec9-112">окне Флаги для изменения поведения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="81ec9-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="81ec9-113">Этот параметр содержит ровно один бит из перечисления [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="81ec9-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="81ec9-114">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="81ec9-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="81ec9-115">`pvReserved`должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="81ec9-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81ec9-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="81ec9-116">Remarks</span></span>  
 <span data-ttu-id="81ec9-117">Параметр содержит ровно один бит `ASM_CACHE_FLAGS` из перечисления. `dwFlags`</span><span class="sxs-lookup"><span data-stu-id="81ec9-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81ec9-118">Требования</span><span class="sxs-lookup"><span data-stu-id="81ec9-118">Requirements</span></span>  
 <span data-ttu-id="81ec9-119">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81ec9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81ec9-120">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="81ec9-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="81ec9-121">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="81ec9-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81ec9-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81ec9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ec9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="81ec9-123">See also</span></span>

- [<span data-ttu-id="81ec9-124">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="81ec9-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="81ec9-125">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="81ec9-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="81ec9-126">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="81ec9-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
