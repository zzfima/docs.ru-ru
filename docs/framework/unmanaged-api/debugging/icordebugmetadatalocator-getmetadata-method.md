---
title: "Метод ICorDebugMetaDataLocator::GetMetaData"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4883ee56c7dd027f053dd072d7c8613f606ff2be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="e842a-102">Метод ICorDebugMetaDataLocator::GetMetaData</span><span class="sxs-lookup"><span data-stu-id="e842a-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="e842a-103">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="e842a-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e842a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e842a-104">Syntax</span></span>  
  
```  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e842a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e842a-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="e842a-106">[in] Завершающаяся нулевым байтом строка, представляющая полный путь к файлу.</span><span class="sxs-lookup"><span data-stu-id="e842a-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="e842a-107">Если полный путь недоступен, имя и расширение файла (*filename*. *расширение*).</span><span class="sxs-lookup"><span data-stu-id="e842a-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="e842a-108">[in] Временная метка из заголовков PE-файла образа.</span><span class="sxs-lookup"><span data-stu-id="e842a-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="e842a-109">Этот параметр потенциально может использоваться для сервера символов ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) уточняющего запроса.</span><span class="sxs-lookup"><span data-stu-id="e842a-109">This parameter can potentially be used for a symbol server ([SymSrv](http://msdn.microsoft.com/library/cc266470.aspx)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="e842a-110">[in] Размер образа из заголовков PE-файла.</span><span class="sxs-lookup"><span data-stu-id="e842a-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="e842a-111">Этот параметр может использоваться для поиска SymSrv.</span><span class="sxs-lookup"><span data-stu-id="e842a-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="e842a-112">[in] Количество символов в `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="e842a-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="e842a-113">[out] Количество `WCHAR`, записанных в `wszPathBuffer`.</span><span class="sxs-lookup"><span data-stu-id="e842a-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="e842a-114">Если метод возвращает E_NOT_SUFFICIENT_BUFFER, содержит число `WCHAR`, необходимых для сохранения пути.</span><span class="sxs-lookup"><span data-stu-id="e842a-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="e842a-115">[out] Указатель на буфер, в который отладчик будет копировать полный путь к файлу, содержащему запрошенные метаданные.</span><span class="sxs-lookup"><span data-stu-id="e842a-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="e842a-116">`ofReadOnly` Флаг из [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) перечисление используется для запроса доступа только для чтения к метаданным в этом файле.</span><span class="sxs-lookup"><span data-stu-id="e842a-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e842a-117">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e842a-117">Return Value</span></span>  
 <span data-ttu-id="e842a-118">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="e842a-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="e842a-119">Все остальные ошибочные значения HRESULT указывают, что файл не удается найти.</span><span class="sxs-lookup"><span data-stu-id="e842a-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="e842a-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e842a-120">HRESULT</span></span>|<span data-ttu-id="e842a-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e842a-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e842a-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="e842a-122">S_OK</span></span>|<span data-ttu-id="e842a-123">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e842a-123">The method completed successfully.</span></span> <span data-ttu-id="e842a-124">`wszPathBuffer` содержит полный путь к файлу и завершается нулевым байтом.</span><span class="sxs-lookup"><span data-stu-id="e842a-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="e842a-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="e842a-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="e842a-126">Текущий размер `wszPathBuffer` недостаточен для хранения полного пути.</span><span class="sxs-lookup"><span data-stu-id="e842a-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="e842a-127">В этом случае `pcchPathBuffer` содержит необходимое количество `WCHAR`, включая завершающий символ null, и `GetMetaData` вызывается второй раз с запрошенным размером буфера.</span><span class="sxs-lookup"><span data-stu-id="e842a-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e842a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e842a-128">Remarks</span></span>  
 <span data-ttu-id="e842a-129">Если `wszImagePath` содержит полный путь для модуля из дампа, он указывает путь с компьютера, на котором был создан дамп.</span><span class="sxs-lookup"><span data-stu-id="e842a-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="e842a-130">Файл может не существовать в этом расположении, или по этому пути может храниться неправильный файл с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="e842a-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e842a-131">Требования</span><span class="sxs-lookup"><span data-stu-id="e842a-131">Requirements</span></span>  
 <span data-ttu-id="e842a-132">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e842a-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e842a-133">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e842a-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e842a-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e842a-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e842a-135">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e842a-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e842a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e842a-136">See Also</span></span>  
 [<span data-ttu-id="e842a-137">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="e842a-137">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [<span data-ttu-id="e842a-138">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="e842a-138">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="e842a-139">Отладка</span><span class="sxs-lookup"><span data-stu-id="e842a-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
