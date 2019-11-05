---
title: Функция QualifierSet_Next (Справочник по неуправляемым API)
description: Функция QualifierSet_Next извлекает следующий квалификатор в перечислении.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c9c824b0158618848c13183d92f88604460d5099
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141725"
---
# <a name="qualifierset_next-function"></a>Функция QualifierSet_Next
Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`   
окне Этот параметр не используется.

`ptr`   
окне Указатель на экземпляр [ивбемкуалифиерсет](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

`lFlags`   
[in] Зарезервировано. Этот параметр должен иметь значение 0.

`pstrName`   
заполняет Имя квалификатора. Если `null`, этот параметр игнорируется. в противном случае `pstrName` не должен указывать на допустимый `BSTR` или на утечку памяти. Если значение не равно null, функция всегда выделяет новую `BSTR`, когда она возвращает `WBEM_S_NO_ERROR`.

`pVal`   
заполняет В случае успеха значение квалификатора. Если функция завершается ошибкой, `VARIANT`, на которую указывает `pVal`, не изменяется. Если этот параметр имеет значение `null`, параметр игнорируется.

`plFlavor`   
заполняет Указатель на значение типа LONG, которое получает флаг квалификатора. Если сведения о разновидностях не нужны, этот параметр можно `null`. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |значения  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Вызывающий объект не вызывал [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении не осталось квалификаторов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .

Вы вызываете функцию `QualifierSet_Next` многократно, чтобы перечислить все квалификаторы, пока функция не вернет `WBEM_S_NO_MORE_DATA`. Чтобы завершить перечисление раньше, вызовите функцию [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .

Порядок квалификаторов, возвращаемых во время перечисления, не определен.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
