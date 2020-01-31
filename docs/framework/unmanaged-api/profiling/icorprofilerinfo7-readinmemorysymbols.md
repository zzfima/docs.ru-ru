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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868347"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="805e6-102">ICorProfilerInfo7:: Реадинмеморисимболс</span><span class="sxs-lookup"><span data-stu-id="805e6-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="805e6-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="805e6-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="805e6-104">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="805e6-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805e6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="805e6-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="805e6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="805e6-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="805e6-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="805e6-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="805e6-108">окне Смещение в потоке в памяти, с которого начинается чтение байтов.</span><span class="sxs-lookup"><span data-stu-id="805e6-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="805e6-109">заполняет Указатель на буфер, в который будут копироваться данные.</span><span class="sxs-lookup"><span data-stu-id="805e6-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="805e6-110">Буфер должен иметь `countSymbolBytes` доступного пространства.</span><span class="sxs-lookup"><span data-stu-id="805e6-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="805e6-111">окне Число байтов для копирования.</span><span class="sxs-lookup"><span data-stu-id="805e6-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="805e6-112">заполняет При возврате из метода содержит фактическое число считанных байтов.</span><span class="sxs-lookup"><span data-stu-id="805e6-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="805e6-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="805e6-113">Return Value</span></span>  
 <span data-ttu-id="805e6-114">`S_OK`, если было считано ненулевое число байтов.</span><span class="sxs-lookup"><span data-stu-id="805e6-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="805e6-115">`CORPROF_E_MODULE_IS_DYNAMIC`, если модуль был создан с помощью <xref:System.Reflection.Emit>.</span><span class="sxs-lookup"><span data-stu-id="805e6-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="805e6-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="805e6-116">Remarks</span></span>  
 <span data-ttu-id="805e6-117">Метод `ReadInMemorySymbols` пытается считать `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти.</span><span class="sxs-lookup"><span data-stu-id="805e6-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="805e6-118">Данные копируются в `pSymbolBytes`, что предполагает наличие `countSymbolBytes` свободного места.</span><span class="sxs-lookup"><span data-stu-id="805e6-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="805e6-119">`pCountSymbolsBytesRead` содержит фактическое число считанных байтов, которое может быть меньше `countSymbolBytes` по достижении конца потока.</span><span class="sxs-lookup"><span data-stu-id="805e6-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="805e6-120">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="805e6-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="805e6-121">Если модуль был создан с помощью отражения. Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="805e6-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="805e6-122">Требования</span><span class="sxs-lookup"><span data-stu-id="805e6-122">Requirements</span></span>  
 <span data-ttu-id="805e6-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="805e6-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805e6-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="805e6-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="805e6-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="805e6-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="805e6-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805e6-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805e6-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="805e6-127">See also</span></span>

- [<span data-ttu-id="805e6-128">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="805e6-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
