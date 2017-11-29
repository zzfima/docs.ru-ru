---
title: "Метод ICLRDataTarget3::GetExceptionRecord"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8c9ac4ecc0cffda4038129b1244b81501e9a1f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a>Метод ICLRDataTarget3::GetExceptionRecord
Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом. Например, для целевого объекта дампа это бы эквивалентно записи исключения, переданной через `ExceptionParam` аргумент [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) функции отладки справки библиотеки Windows (DbgHelp).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `bufferSize`  
 [в] Размер входного буфера в байтах. Это должен быть равен `sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.  
  
 `bufferUsed`  
 [из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.  
  
 `buffer`  
 [из] Указатель на буфер памяти, который получает копию записи исключения. Запись исключения возвращается в виде [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Запись исключения скопирована в буфер вывода.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Нет записей исключения, связанных с целевым объектом.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Размер входного буфера не равен `sizeof(MINIDUMP_EXCEPTION)`.|  
  
## <a name="remarks"></a>Примечания  
 [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) — это структура, определенные в файлах dbghelp.h и IMAGEHLP.h, входящих в состав Windows SDK пакета.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [Метод GetExceptionContextRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [Метод GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
