---
title: "Функция GetDemultiplexedStub (Справочник по неуправляемым API)"
description: "Функция GetDemultiplexedStub создает приемника объектов сервера пересылки для клиента при получении асинхронные вызовы от управления Windows."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a81101acbf65546ea068e6b5a0e8d9045aaadc71
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="getdemultiplexedstub-function"></a>Функция GetDemultiplexedStub
Создает приемник объект сервера пересылки для клиента при получении асинхронные вызовы от управления Windows.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>Параметры

`pObject`  
[in] Указатель на реализацию клиента в процессе [IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx).

`isLocal`  
[in] Флаг, который указывает, является ли событие локального (`true`); в противном случае `false`.

`ppObject`  
[out] Объект сервера пересылки приемник для клиента при получении асинхронные вызовы от управления Windows.

## <a name="return-value"></a>Возвращаемое значение

Если функция выполняется успешно, возвращаемое значение равно `S_OK` (0).

Если функция завершается с ошибкой, возвращается код ошибки ненулевое значение. Чтобы получить расширенные сведения об ошибке, вызовите [GetErrorInfo](geterrorinfo.md) функции.
    
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
