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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97a19f236b87a7f4c5b2014aca6ee4abd338c63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798282"
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
заполняет Имя квалификатора. Значение, если `null`этот параметр не учитывается; в противном случае не `BSTR` долженуказыватьнадопустимыйилиутечкупамяти.`pstrName` Если значение не равно null, функция всегда выделяет новый `BSTR` при возврате. `WBEM_S_NO_ERROR`

`pVal`   
заполняет В случае успеха значение квалификатора. Если функция завершается ошибкой, `VARIANT` то, на `pVal` которую указывает, не изменяется. Если этот параметр имеет `null`значение, параметр игнорируется.

`plFlavor`   
заполняет Указатель на значение типа LONG, которое получает флаг квалификатора. Если сведения о разновидностях не нужны, этот параметр может `null`иметь значение. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определены в файле заголовка *вбемкли. h* , или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Вызывающий объект не вызывал [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для начала нового перечисления. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении не осталось квалификаторов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции выполнен успешно.  |
  
## <a name="remarks"></a>Примечания

Эта функция заключает в оболочку вызов метода [ивбемкуалифиерсет:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) .

`QualifierSet_Next` Функция вызывается повторно для перечисления всех квалификаторов до возвращения `WBEM_S_NO_MORE_DATA`функции. Чтобы завершить перечисление раньше, вызовите функцию [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) .

Порядок квалификаторов, возвращаемых во время перечисления, не определен.

## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
