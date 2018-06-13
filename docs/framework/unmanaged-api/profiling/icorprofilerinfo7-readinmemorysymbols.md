---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9874c8e567a89fd3977be360666c86406f2cd395
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455935"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="57aa0-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="57aa0-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="57aa0-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="57aa0-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="57aa0-104">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="57aa0-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57aa0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57aa0-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="57aa0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="57aa0-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="57aa0-107">[in] Идентификатор модуля, содержащего потока в памяти.</span><span class="sxs-lookup"><span data-stu-id="57aa0-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="57aa0-108">[in] Смещение в поток в памяти, с которого начинается чтение байтов.</span><span class="sxs-lookup"><span data-stu-id="57aa0-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="57aa0-109">[out] Указатель на буфер, в который будут копироваться данные.</span><span class="sxs-lookup"><span data-stu-id="57aa0-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="57aa0-110">Буфер должен иметь `countSymbolBytes` доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="57aa0-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="57aa0-111">[in] Число байтов для копирования.</span><span class="sxs-lookup"><span data-stu-id="57aa0-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="57aa0-112">[out] При возвращении метода содержит фактическое число считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="57aa0-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57aa0-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="57aa0-113">Return Value</span></span>  
 <span data-ttu-id="57aa0-114">`S_OK`, если были считаны ненулевое число байтов.</span><span class="sxs-lookup"><span data-stu-id="57aa0-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="57aa0-115">`CORPROF_E_MODULE_IS_DYNAMIC`, если модуль был создан с помощью <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="57aa0-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57aa0-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="57aa0-116">Remarks</span></span>  
 <span data-ttu-id="57aa0-117">`ReadInMemorySymbols` Метод пытается считать `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти.</span><span class="sxs-lookup"><span data-stu-id="57aa0-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="57aa0-118">Данные копируются в `pSymbolBytes`, который должен иметь `countSymbolBytes` доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="57aa0-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="57aa0-119">`pCountSymbolsBytesRead` содержит фактическое число байтов, чтение, которое может быть меньше, чем `countSymbolBytes` если достигнут конец потока.</span><span class="sxs-lookup"><span data-stu-id="57aa0-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57aa0-120">Текущая реализация не поддерживает Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="57aa0-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="57aa0-121">Если модуль был создан с помощью Reflection.Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="57aa0-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57aa0-122">Требования</span><span class="sxs-lookup"><span data-stu-id="57aa0-122">Requirements</span></span>  
 <span data-ttu-id="57aa0-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57aa0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57aa0-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="57aa0-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="57aa0-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57aa0-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57aa0-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57aa0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57aa0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="57aa0-127">See Also</span></span>  
 [<span data-ttu-id="57aa0-128">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="57aa0-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
