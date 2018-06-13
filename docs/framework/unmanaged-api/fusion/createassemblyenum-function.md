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
ms.openlocfilehash: b2098d5d9ce1c01f232cf2904c1fd3e990dfbe2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432120"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="a2c70-102">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a2c70-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="a2c70-103">Возвращает указатель на [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) экземпляр, предназначенный для перечисления объектов в сборке с указанным [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a2c70-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c70-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2c70-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2c70-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2c70-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="a2c70-106">[out] Указатель на область памяти, содержащей запрошенный `IAssemblyEnum` указателя.</span><span class="sxs-lookup"><span data-stu-id="a2c70-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="a2c70-107">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="a2c70-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a2c70-108">`pUnkReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="a2c70-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="a2c70-109">[in] `IAssemblyName` Запрошенной сборки.</span><span class="sxs-lookup"><span data-stu-id="a2c70-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="a2c70-110">Это имя используется для фильтрации перечисления.</span><span class="sxs-lookup"><span data-stu-id="a2c70-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="a2c70-111">Он может быть null для перечисления всех сборок в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="a2c70-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a2c70-112">[in] Флаги для изменения поведения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="a2c70-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="a2c70-113">Этот параметр содержит ровно один бит из [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="a2c70-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a2c70-114">[in] Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="a2c70-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a2c70-115">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="a2c70-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2c70-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2c70-116">Remarks</span></span>  
 <span data-ttu-id="a2c70-117">`dwFlags` Параметр содержит ровно один бит из `ASM_CACHE_FLAGS` перечисления.</span><span class="sxs-lookup"><span data-stu-id="a2c70-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2c70-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a2c70-118">Requirements</span></span>  
 <span data-ttu-id="a2c70-119">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2c70-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2c70-120">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a2c70-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a2c70-121">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2c70-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2c70-122">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2c70-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c70-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a2c70-123">See Also</span></span>  
 [<span data-ttu-id="a2c70-124">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="a2c70-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 [<span data-ttu-id="a2c70-125">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="a2c70-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="a2c70-126">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="a2c70-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
