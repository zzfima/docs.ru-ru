---
title: Метод ICLRDataTarget3::GetExceptionRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a43863477e902f6f02007ba291a25d2469283e91
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425176"
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="9dbb1-102">Метод ICLRDataTarget3::GetExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="9dbb1-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="9dbb1-103">Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="9dbb1-104">Например, для целевого объекта дампа, это будет эквивалентно записи исключения, переданной через `ExceptionParam` аргумент [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) функции в Windows отладка библиотеки справки (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="9dbb1-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dbb1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9dbb1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9dbb1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9dbb1-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="9dbb1-107">[в] Размер входного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="9dbb1-108">Это должно быть равно `sizeof(` [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="9dbb1-109">[из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9dbb1-110">[из] Указатель на буфер памяти, который получает копию записи исключения.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="9dbb1-111">Запись исключения возвращается в виде [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) типа.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-111">The exception record is returned as a [MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9dbb1-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9dbb1-112">Return Value</span></span>  
 <span data-ttu-id="9dbb1-113">Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="9dbb1-114">Коды `HRESULT` могут включать значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="9dbb1-115">Код возврата</span><span class="sxs-lookup"><span data-stu-id="9dbb1-115">Return code</span></span>|<span data-ttu-id="9dbb1-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9dbb1-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="9dbb1-117">Метод успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-117">Method succeeded.</span></span> <span data-ttu-id="9dbb1-118">Запись исключения скопирована в буфер вывода.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="9dbb1-119">Нет записей исключения, связанных с целевым объектом.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="9dbb1-120">Размер входного буфера не равен `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dbb1-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="9dbb1-121">Remarks</span></span>  
 <span data-ttu-id="9dbb1-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) — это структура, определенные в файлах dbghelp.h и IMAGEHLP.h, входящих с состав пакета Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-122">[MINIDUMP_EXCEPTION](/windows/desktop/api/minidumpapiset/ns-minidumpapiset-_minidump_exception) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="9dbb1-123">Этот метод реализуется модулем записи отладчика.</span><span class="sxs-lookup"><span data-stu-id="9dbb1-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dbb1-124">Требования</span><span class="sxs-lookup"><span data-stu-id="9dbb1-124">Requirements</span></span>  
 <span data-ttu-id="9dbb1-125">**Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dbb1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dbb1-126">**Заголовок:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9dbb1-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9dbb1-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dbb1-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dbb1-128">**Версии платформы .NET Framework:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dbb1-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dbb1-129">См. также</span><span class="sxs-lookup"><span data-stu-id="9dbb1-129">See Also</span></span>  
 [<span data-ttu-id="9dbb1-130">Интерфейс ICLRDataTarget3</span><span class="sxs-lookup"><span data-stu-id="9dbb1-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="9dbb1-131">Метод GetExceptionContextRecord</span><span class="sxs-lookup"><span data-stu-id="9dbb1-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="9dbb1-132">Метод GetExceptionThreadID</span><span class="sxs-lookup"><span data-stu-id="9dbb1-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
