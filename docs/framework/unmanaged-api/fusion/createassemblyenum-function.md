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
ms.openlocfilehash: d809bbfa17ed9e9ae16505852740e874ca11248c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621790"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="f6480-102">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f6480-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="f6480-103">Возвращает указатель на [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) экземпляр, который может перечислить объекты в сборке с указанным [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f6480-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6480-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6480-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6480-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f6480-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="f6480-106">[out] Указатель на область памяти, который содержит требуемый `IAssemblyEnum` указатель.</span><span class="sxs-lookup"><span data-stu-id="f6480-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="f6480-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="f6480-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f6480-108">`pUnkReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="f6480-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="f6480-109">[in] `IAssemblyName` Запрошенной сборки.</span><span class="sxs-lookup"><span data-stu-id="f6480-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="f6480-110">Это имя используется для фильтрации перечисления.</span><span class="sxs-lookup"><span data-stu-id="f6480-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="f6480-111">Он может иметь значение null для перечисления всех сборок в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="f6480-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f6480-112">[in] Флаги для изменения поведения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="f6480-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="f6480-113">Этот параметр содержит ровно один бит из [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="f6480-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="f6480-114">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="f6480-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="f6480-115">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="f6480-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6480-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6480-116">Remarks</span></span>  
 <span data-ttu-id="f6480-117">`dwFlags` Параметр содержит ровно один бит из `ASM_CACHE_FLAGS` перечисления.</span><span class="sxs-lookup"><span data-stu-id="f6480-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6480-118">Требования</span><span class="sxs-lookup"><span data-stu-id="f6480-118">Requirements</span></span>  
 <span data-ttu-id="f6480-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6480-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6480-120">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="f6480-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f6480-121">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f6480-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6480-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6480-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6480-123">См. также</span><span class="sxs-lookup"><span data-stu-id="f6480-123">See also</span></span>
- [<span data-ttu-id="f6480-124">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f6480-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="f6480-125">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="f6480-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="f6480-126">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="f6480-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
