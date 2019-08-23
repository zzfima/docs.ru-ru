---
title: 'ICorProfilerInfo7:: Реадинмеморисимболс'
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
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955374"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="2f096-102">ICorProfilerInfo7:: Реадинмеморисимболс</span><span class="sxs-lookup"><span data-stu-id="2f096-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="2f096-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="2f096-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="2f096-104">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="2f096-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f096-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f096-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f096-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f096-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="2f096-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="2f096-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="2f096-108">окне Смещение в потоке в памяти, с которого начинается чтение байтов.</span><span class="sxs-lookup"><span data-stu-id="2f096-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="2f096-109">заполняет Указатель на буфер, в который будут копироваться данные.</span><span class="sxs-lookup"><span data-stu-id="2f096-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="2f096-110">Буфер должен иметь `countSymbolBytes` доступное место.</span><span class="sxs-lookup"><span data-stu-id="2f096-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="2f096-111">окне Число байтов для копирования.</span><span class="sxs-lookup"><span data-stu-id="2f096-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="2f096-112">заполняет При возврате из метода содержит фактическое число считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="2f096-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f096-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f096-113">Return Value</span></span>  
 <span data-ttu-id="2f096-114">`S_OK`значение, если было считано ненулевое число байтов.</span><span class="sxs-lookup"><span data-stu-id="2f096-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="2f096-115">`CORPROF_E_MODULE_IS_DYNAMIC`, если модуль был создан с помощью <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="2f096-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f096-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="2f096-116">Remarks</span></span>  
 <span data-ttu-id="2f096-117">Метод пытается выполнить чтение `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти. `ReadInMemorySymbols`</span><span class="sxs-lookup"><span data-stu-id="2f096-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="2f096-118">Данные копируются в `pSymbolBytes`, что должно иметь `countSymbolBytes` доступное место.</span><span class="sxs-lookup"><span data-stu-id="2f096-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="2f096-119">`pCountSymbolsBytesRead`содержит фактическое число считанных байтов, которое может быть меньше, `countSymbolBytes` чем при достижении конца потока.</span><span class="sxs-lookup"><span data-stu-id="2f096-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f096-120">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="2f096-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="2f096-121">Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`значение.</span><span class="sxs-lookup"><span data-stu-id="2f096-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f096-122">Требования</span><span class="sxs-lookup"><span data-stu-id="2f096-122">Requirements</span></span>  
 <span data-ttu-id="2f096-123">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f096-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f096-124">**Заголовок.** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="2f096-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f096-125">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="2f096-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f096-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f096-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f096-127">См. также</span><span class="sxs-lookup"><span data-stu-id="2f096-127">See also</span></span>

- [<span data-ttu-id="2f096-128">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="2f096-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
