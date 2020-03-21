---
title: Функция GetDemultiplexedStub (Неуправляемая справка API)
description: Функция GetDemultiplexedStub создает поглотитель антока объекта, чтобы помочь клиенту в получении асинхронных звонков от управления Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174970"
---
# <a name="getdemultiplexedstub-function"></a>Функция GetDemultiplexedStub
Создает приемник переадресации объекта, который помогает клиенту получать асинхронные вызовы из службы управления Windows.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a>Параметры

`pObject`  
(в) Указатель на процесс реализации клиента [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
(в) Флаг, указывающий, является ли`true`событие локальным (); в `false`противном случае, .

`ppObject`  
(ваут) Объект-форвард тонет, чтобы помочь клиенту в получении асинхронных звонков от управления Windows.

## <a name="return-value"></a>Возвращаемое значение

Если функция успешно, значение возврата `S_OK` (0).

Если функция выходит из строя, значение возврата является ненулевым кодом ошибки. Чтобы получить расширенную информацию об ошибке, позвоните в функцию [GetErrorInfo.](geterrorinfo.md)

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
