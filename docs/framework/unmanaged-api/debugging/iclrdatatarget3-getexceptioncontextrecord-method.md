---
title: Метод ICLRDataTarget3::GetExceptionContextRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b43ab8cdeff3866bb51e8634f367cf86ee483d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089235"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Метод ICLRDataTarget3::GetExceptionContextRecord
Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом. Например, для целевого объекта дампа, это будет эквивалентно записи контекста, переданной через `ExceptionParam` аргумент [MiniDumpWriteDump](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) функции в Windows отладка библиотеки справки (DbgHelp).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bufferSize`  
 [в] Размер входного буфера в байтах. Он должен быть достаточно большим, чтобы вместить запись контекста.  
  
 `bufferUsed`  
 [из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.  
  
 `buffer`  
 [из] Указатель на буфер памяти, который получает копию записи контекста. Запись исключения возвращается в виде [контекст](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) типа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Запись контекста скопирована в буфер вывода.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Нет записей контекста, связанных с целевым объектом.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Размер входного буфера недостаточен для сохранения записи контекста.|  
  
## <a name="remarks"></a>Примечания  
 [КОНТЕКСТ](/windows/desktop/api/winnt/ns-winnt-_arm64_nt_context) — это структура платформы, определенные в заголовки, предоставляемые пакетом SDK для Windows.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** ClrData.idl, ClrData.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget3](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [Метод GetExceptionRecord](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
- [Метод GetExceptionThreadID](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)
