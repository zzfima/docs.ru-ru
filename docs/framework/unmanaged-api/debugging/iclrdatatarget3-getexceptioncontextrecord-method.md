---
title: "Метод ICLRDataTarget3::GetExceptionContextRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetContextRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c2e645222553f4000b300fa4f010ff81ff44d23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Метод ICLRDataTarget3::GetExceptionContextRecord
Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом. Например, для целевого объекта дампа это бы эквивалентно записи контекста, переданной через `ExceptionParam` аргумент [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360\(v=vs.85\).aspx) функции отладки справки библиотеки Windows (DbgHelp).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bufferSize`  
 [в] Размер входного буфера в байтах. Он должен быть достаточно большим, чтобы вместить запись контекста.  
  
 `bufferUsed`  
 [из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.  
  
 `buffer`  
 [из] Указатель на буфер памяти, который получает копию записи контекста. Запись исключения возвращается в виде [КОНТЕКСТА](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Запись контекста скопирована в буфер вывода.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Нет записей контекста, связанных с целевым объектом.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Размер входного буфера недостаточен для сохранения записи контекста.|  
  
## <a name="remarks"></a>Примечания  
 [КОНТЕКСТ](http://msdn.microsoft.com/library/windows/desktop/ms679284\(v=vs.85\).aspx) является от платформы структура, определенная в заголовки, предоставляемые пакетом SDK для Windows.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [Метод GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)  
 [Метод GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
