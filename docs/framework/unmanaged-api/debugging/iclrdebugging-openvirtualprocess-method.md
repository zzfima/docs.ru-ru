---
title: Метод ICLRDebugging::OpenVirtualProcess
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cae30dbd1ae9081334e2ff890e1e4cd167a66e04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586334"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>Метод ICLRDebugging::OpenVirtualProcess
Получает интерфейс ICorDebugProcess, соответствующий общий язык среды выполнения (CLR) модуль загружается в процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleBaseAddress`  
 [in] Базовый адрес модуля в целевом процессе. COR_E_NOT_CLR возвращается, если указанный модуль не является модулем CLR.  
  
 `pDataTarget`  
 [in] Целевой уровень абстракции данных, позволяющий управляемый отладчик к проверяемому состоянию процесса. Отладчик должен реализовывать [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейс. Следует реализовать [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейс для поддержки сценариев, где среда CLR отлаживаемом не устанавливается локально на компьютере.  
  
 `pLibraryProvider`  
 [in] Интерфейс обратного вызова поставщика библиотеки, который позволяет конкретной версии библиотеки отладки находить и загружать по требованию. Этот параметр является обязательным только в том случае, если `ppProcess` или `pFlags` не `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] Самую новую версию среды CLR, способное отлаживать этот отладчик. Следует указать основной и дополнительный номера и версии из последней версии среды CLR, которые поддерживает этот отладчик сборок, а также задавать номер редакции до 65 535, чтобы вместить будущих CLR на месте, обслуживающие выпуски.  
  
 `riidProcess`  
 [in] Идентификатор ICorDebugProcess-интерфейс для извлечения. В настоящее время допустимы только значения являются IID_CORDEBUGPROCESS3 IID_CORDEBUGPROCESS2 и IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 [out] Указатель на COM-интерфейс, который определяется параметром `riidProcess`.  
  
 `pVersion`  
 [in, out] Версия среды CLR. Во входных данных, это значение может быть `null`. Он также может указывать [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) структура, в противном случае структура `wStructVersion` поля должен быть инициализирован в 0 (ноль).  
  
 На выходе, возвращенный `CLR_DEBUGGING_VERSION` структуры будут заполнены сведения о версии среды CLR.  
  
 `pdwFlags`  
 [out] Информационные флаги для указанной среды выполнения. См. в разделе [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) разделе Описание флагов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Свойство `pDataTarget` имеет значение `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) обратный вызов возвращает ошибку, или не поддерживает допустимый дескриптор.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget` не реализует необходимые интерфейсы целевых данных для этой версии среды выполнения.|  
|CORDBG_E_NOT_CLR|Указанный модуль не является модулем CLR. Данный HRESULT также возвращается, если не удается обнаружить модуль среды CLR, поскольку память повреждена, модуль не доступен или более поздней, чем версия оболочки версию среды CLR.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Эта версия среды выполнения не поддерживает данную модель отладки. В настоящее время эта модель отладки не поддерживается версиями CLR до [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. `pwszVersion` Выходные данные по-прежнему установлено правильное значение после данной ошибки.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Версия среды CLR больше, чем версии, которую этот отладчик утверждений для поддержки. `pwszVersion` Выходные данные по-прежнему установлено правильное значение после данной ошибки.|  
|E_NO_INTERFACE|`riidProcess` Интерфейс недоступен.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|`CLR_DEBUGGING_VERSION` Структура не является распознанным значением `wStructVersion`. В настоящее время единственным допустимым значением является 0.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
