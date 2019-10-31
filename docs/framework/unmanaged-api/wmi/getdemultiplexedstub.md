---
title: Функция Жетдемултиплекседстуб (Справочник по неуправляемым API)
description: Функция Жетдемултиплекседстуб создает приемник сервера пересылки объектов, чтобы помочь клиенту получать асинхронные вызовы из управления Windows.
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
ms.openlocfilehash: 9cc028b3300b43f8a0fb3e29f8b5ac6e1817b8c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127471"
---
# <a name="getdemultiplexedstub-function"></a>Функция Жетдемултиплекседстуб
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
окне Указатель на внутрипроцессный клиентскую реализацию [ивбемобжектсинк](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
окне Флаг, указывающий, является ли событие локальным (`true`); в противном случае `false`.

`ppObject`  
заполняет Приемник объекта сервера пересылки, который помогает клиенту получать асинхронные вызовы из управления Windows.

## <a name="return-value"></a>Возвращаемое значение

Если функция выполнена удачно, возвращается значение `S_OK` (0).

Если функция завершается ошибкой, возвращаемое значение является ненулевым кодом ошибки. Чтобы получить расширенные сведения об ошибке, вызовите функцию [жетерроринфо](geterrorinfo.md) .
    
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
