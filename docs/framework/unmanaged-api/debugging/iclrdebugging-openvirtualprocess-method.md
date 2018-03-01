---
title: "Метод ICLRDebugging::OpenVirtualProcess"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f1f71f42f10c3d25714998d1697b20a5ee13e055
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>Метод ICLRDebugging::OpenVirtualProcess
Получает интерфейс ICorDebugProcess, соответствующий общие модуля среды CLR (CLR) загружена в процессе.  
  
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
 [in] Целевой уровень абстракции данных, позволяющий управляемый отладчик для проверки состояния процесса. Отладчик должен реализовывать [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) интерфейса. Вам следует реализовать [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) интерфейс для поддержки сценариев, где отлаживаемой среды CLR не установлена локально на компьютере.  
  
 `pLibraryProvider`  
 [in] Интерфейс обратного вызова поставщика библиотеки, который позволяет зависящие от версии библиотеки отладки находить и загружать по требованию. Этот параметр является обязательным только в том случае, если `ppProcess` или `pFlags` не `null`.  
  
 `pMaxDebuggerSupportedVersion`  
 [in] Более высокая версия CLR, можно отлаживать этот отладчик. Необходимо указать основной и дополнительный номера и версию последнюю версию среды CLR, поддерживаемой этим отладчиком построения и номер редакции равно 65 535, чтобы вместить будущих обслуживания версий среды CLR на месте.  
  
 `riidProcess`  
 [in] Идентификатор ICorDebugProcess-интерфейс для извлечения. В настоящее время допустимы только значения, IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 и IID_CORDEBUGPROCESS.  
  
 `ppProcess`  
 [out] Указатель на COM-интерфейс, который определяется параметром `riidProcess`.  
  
 `pVersion`  
 [in, out] Версия среды CLR. На входе, это значение может быть `null`. Она также может указывать на [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) структура, в этом случае структура `wStructVersion` поле должно быть инициализировано 0 (ноль).  
  
 На выходе возвращенная `CLR_DEBUGGING_VERSION` структуры будут заполнены сведения о версии для среды CLR.  
  
 `pdwFlags`  
 [out] Информационные флаги заданной средой выполнения. В разделе [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) разделе Описание флагов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Свойство `pDataTarget` имеет значение `null`.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) обратного вызова возвращает сообщение об ошибке или не предоставлен допустимый дескриптор.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`не реализует необходимые интерфейсы целевых данных для этой версии среды выполнения.|  
|CORDBG_E_NOT_CLR|Указанный модуль не является модулем CLR. Это значение HRESULT также возвращается, если не удается обнаружить модуль среды CLR, так как память повреждена, модуль недоступен или более поздней, чем версия оболочки версию среды CLR.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|Эта версия среды выполнения не поддерживает данную модель отладки. В настоящее время эта модель отладки не поддерживается версиями CLR перед [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. `pwszVersion` Выходной параметр по-прежнему задано правильное значение после данной ошибки.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|Версии среды CLR больше, чем версия этот отладчик для поддержки утверждения. `pwszVersion` Выходной параметр по-прежнему задано правильное значение после данной ошибки.|  
|E_NO_INTERFACE|`riidProcess` Интерфейс недоступен.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|`CLR_DEBUGGING_VERSION` Структура не имеет является распознанным значением `wStructVersion`. В настоящее время единственным допустимым значением является 0.|  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="remarks"></a>Примечания  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
