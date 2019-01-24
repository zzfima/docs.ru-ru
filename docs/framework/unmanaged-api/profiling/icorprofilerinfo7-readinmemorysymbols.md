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
ms.openlocfilehash: ca71819214e614af5a0c269ed77b1cf7f9b7d7ee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658680"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a>ICorProfilerInfo7::ReadInMemorySymbols
[Поддерживается в [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] и более поздних версиях]  
  
 Считывает байт из потока символов в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, содержащего поток в памяти.  
  
 `symbolsReadOffset`  
 [in] Смещение в поток в памяти, с которого начинается чтение байтов.  
  
 `pSymbolBytes`  
 [out] Указатель на буфер, в который будут копироваться данные. Буфер должен иметь `countSymbolBytes` доступного пространства.  
  
 `countSymbolBytes`  
 [in] Число байтов для копирования.  
  
 `pCountSymbolBytesRead`  
 [out] При возвращении метода содержит фактическое число считанных байтов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если были считаны ненулевое число байтов.  
  
 `CORPROF_E_MODULE_IS_DYNAMIC`, если модуль был создан с помощью <xref:System.Reflection.Emit>.  
  
## <a name="remarks"></a>Примечания  
 `ReadInMemorySymbols` Метод пытается считать `countSymbolBytes` данных, начиная со смещения `symbolsReadOffset` в потоке в памяти. Данные копируются `pSymbolBytes`, который должен иметь `countSymbolBytes` доступного пространства.     `pCountSymbolsBytesRead` содержит фактическое число считанных байтов, который может быть меньше, чем `countSymbolBytes` если достигнут конец потока.  
  
> [!NOTE]
>  Текущая реализация не поддерживает Reflection.Emit. Если модуль был создан с помощью Reflection.Emit, метод возвращает `CORPROF_E_MODULE_IS_DYNAMIC`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
