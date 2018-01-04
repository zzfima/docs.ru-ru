---
title: "Функция SpawnInstance (Справочник по неуправляемым API)"
description: "Функция SpawnInstance создает новый экземпляр класса."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SpawnInstance
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SpawnInstance
helpviewer_keywords: SpawnInstance function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68508f3000e7f4ac481f940ef4c715366c37125c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="spawninstance-function"></a>Функция SpawnInstance
Создает новый экземпляр класса.    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppNewInstance`  
[out] Получает указатель на новый экземпляр класса. Если возникает ошибка, новый объект не возвращается, и `ppNewInstance` влево без изменений.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`не является допустимым определением класса и не может создать новые экземпляры. Он неполон или он не был зарегистрирован с помощью управления Windows путем вызова [PutClassWmi](putclasswmi.md). |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Свойство `ppNewClass` имеет значение `null`. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) метод.

`ptr`Определение класса приобретаются у управления Windows. (Обратите внимание, что поддерживается порождает экземпляра из экземпляра, но возвращаемый экземпляр пуст). Затем используйте следующее определение класса для создания новых экземпляров. Вызов [PutInstanceWmi](putinstancewmi.md) функции является обязательным, если планируется указать экземпляр для управления Windows.




Новый объект, возвращаемый в `ppNewClass` автоматически становится подкласс текущего объекта. Нельзя переопределить это поведение. Нет никакой другой метод, с помощью которого создаются подклассы (классы).

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
