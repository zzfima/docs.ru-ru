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
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153326"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="50e1c-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="50e1c-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="50e1c-103">[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="50e1c-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="50e1c-104">Считывает байт из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="50e1c-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e1c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="50e1c-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50e1c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="50e1c-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="50e1c-107">[in] Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="50e1c-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="50e1c-108">[in] Смещение в поток в памяти, с которого начинается чтение байтов.</span><span class="sxs-lookup"><span data-stu-id="50e1c-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="50e1c-109">[out] Указатель на буфер, в который будут копироваться данные.</span><span class="sxs-lookup"><span data-stu-id="50e1c-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="50e1c-110">Буфер должен иметь `countSymbolBytes` доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="50e1c-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="50e1c-111">[in] Число байтов для копирования.</span><span class="sxs-lookup"><span data-stu-id="50e1c-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="50e1c-112">[out] При возвращении метода содержит фактическое число считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="50e1c-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50e1c-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="50e1c-113">Return Value</span></span>  
 `S_OK`<span data-ttu-id="50e1c-114">, если были считаны ненулевое число байтов.</span><span class="sxs-lookup"><span data-stu-id="50e1c-114">, if a non-zero number of bytes were read.</span></span>  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`<span data-ttu-id="50e1c-115">, если модуль был создан с помощью <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="50e1c-115">, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50e1c-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="50e1c-116">Remarks</span></span>  
 <span data-ttu-id="50e1c-117">`ReadInMemorySymbols` Метод пытается считать `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти.</span><span class="sxs-lookup"><span data-stu-id="50e1c-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="50e1c-118">Данные копируются `pSymbolBytes`, который должен иметь `countSymbolBytes` доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="50e1c-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     `pCountSymbolsBytesRead` <span data-ttu-id="50e1c-119">содержит фактическое число считанных байтов, который может быть меньше, чем `countSymbolBytes` если достигнут конец потока.</span><span class="sxs-lookup"><span data-stu-id="50e1c-119">contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50e1c-120">Текущая реализация не поддерживает Reflection.Emit.</span><span class="sxs-lookup"><span data-stu-id="50e1c-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="50e1c-121">Если модуль был создан с помощью Reflection.Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="50e1c-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e1c-122">Требования</span><span class="sxs-lookup"><span data-stu-id="50e1c-122">Requirements</span></span>  
 <span data-ttu-id="50e1c-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e1c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e1c-124">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50e1c-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50e1c-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e1c-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="50e1c-126">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="50e1c-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50e1c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="50e1c-127">See also</span></span>

- [<span data-ttu-id="50e1c-128">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="50e1c-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
