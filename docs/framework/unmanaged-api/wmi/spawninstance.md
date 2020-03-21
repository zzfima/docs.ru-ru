---
title: Функция SpawnInstance (Неуправляемая ссылка API)
description: Функция SpawnInstance создает новый экземпляр класса.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176725"
---
# <a name="spawninstance-function"></a>Функция SpawnInstance
Создает экземпляр класса.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`ppNewInstance`  
(ваут) Получает указатель на новый экземпляр класса. При возникновении ошибки новый объект `ppNewInstance` не возвращается и остается неизмененным.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0x80041020 | `ptr`не является действительным определением класса и не может породить новые экземпляры. Либо она неполная, либо она не была зарегистрирована в управлении Windows, позвонив [в PutClassWmi.](putclasswmi.md) |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр `ppNewClass` равен `null`. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::SpawnInstance.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)

`ptr`должно быть определение класса, полученное от управления Windows. (Обратите внимание, что нерест экземпляра из экземпляра поддерживается, но возвращенный экземпляр пуст.) Затем это определение класса используется для создания новых экземпляров. Если вы намереваетесь написать экземпляр в управление Windows, требуется вызов функции [PutInstanceWmi.](putinstancewmi.md)

Новый объект, `ppNewClass` возвращенный в автоматически становится подклассом текущего объекта. Такое поведение нельзя переопределить. Нет другого метода, с помощью которого могут быть созданы подклассы (производные классы).

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
