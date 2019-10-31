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
ms.openlocfilehash: 0e54027806cef07fad4740c3bf5226fd26c72570
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108781"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="8df5a-102">Функция CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="8df5a-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="8df5a-103">Возвращает указатель на экземпляр [IAssemblyEnum](iassemblyenum-interface.md) , который может перечислить объекты в сборке с указанным [IAssemblyName](iassemblyname-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8df5a-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8df5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8df5a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8df5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8df5a-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="8df5a-106">заполняет Указатель на место в памяти, содержащее запрошенный указатель `IAssemblyEnum`.</span><span class="sxs-lookup"><span data-stu-id="8df5a-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="8df5a-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="8df5a-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8df5a-108">`pUnkReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="8df5a-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="8df5a-109">окне `IAssemblyName` запрошенной сборки.</span><span class="sxs-lookup"><span data-stu-id="8df5a-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="8df5a-110">Это имя используется для фильтрации перечисления.</span><span class="sxs-lookup"><span data-stu-id="8df5a-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="8df5a-111">Для перечисления всех сборок в глобальном кэше сборок может быть задано значение null.</span><span class="sxs-lookup"><span data-stu-id="8df5a-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8df5a-112">окне Флаги для изменения поведения перечислителя.</span><span class="sxs-lookup"><span data-stu-id="8df5a-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="8df5a-113">Этот параметр содержит ровно один бит из перечисления [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8df5a-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8df5a-114">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="8df5a-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="8df5a-115">`pvReserved` должен быть пустой ссылкой.</span><span class="sxs-lookup"><span data-stu-id="8df5a-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8df5a-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="8df5a-116">Remarks</span></span>  
 <span data-ttu-id="8df5a-117">Параметр `dwFlags` содержит ровно один бит из перечисления `ASM_CACHE_FLAGS`.</span><span class="sxs-lookup"><span data-stu-id="8df5a-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8df5a-118">Требования</span><span class="sxs-lookup"><span data-stu-id="8df5a-118">Requirements</span></span>  
 <span data-ttu-id="8df5a-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8df5a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8df5a-120">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="8df5a-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8df5a-121">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8df5a-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8df5a-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8df5a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8df5a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="8df5a-123">See also</span></span>

- [<span data-ttu-id="8df5a-124">Интерфейс IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="8df5a-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="8df5a-125">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="8df5a-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="8df5a-126">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="8df5a-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
