---
title: 'Метод ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: a675cc301d2dd32f87e3864a3123e2044761ef91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868360"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="511fa-102">Метод ICorProfilerInfo7:: GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="511fa-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="511fa-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="511fa-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="511fa-104">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="511fa-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="511fa-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="511fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="511fa-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="511fa-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="511fa-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="511fa-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="511fa-108">пкаунтсимболбитес</span><span class="sxs-lookup"><span data-stu-id="511fa-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="511fa-109">заполняет Указатель на `DWORD` значение, которое при возврате метода содержит длину потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="511fa-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="511fa-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="511fa-110">Return Value</span></span>  
 <span data-ttu-id="511fa-111">Метод возвращает `S_OK`, если длина потока памяти может быть определена, даже если она равна нулю (0).</span><span class="sxs-lookup"><span data-stu-id="511fa-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="511fa-112">Метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`, если метод был создан с помощью <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="511fa-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="511fa-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="511fa-113">Remarks</span></span>  
 <span data-ttu-id="511fa-114">Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="511fa-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="511fa-115">Если у модуля нет символов в памяти, `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="511fa-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="511fa-116">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="511fa-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="511fa-117">Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="511fa-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="511fa-118">Требования</span><span class="sxs-lookup"><span data-stu-id="511fa-118">Requirements</span></span>  
 <span data-ttu-id="511fa-119">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="511fa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="511fa-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="511fa-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="511fa-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="511fa-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="511fa-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="511fa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="511fa-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="511fa-123">See also</span></span>

- [<span data-ttu-id="511fa-124">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="511fa-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
