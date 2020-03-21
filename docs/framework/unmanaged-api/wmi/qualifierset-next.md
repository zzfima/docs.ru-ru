---
title: QualifierSet_Next функция (Неуправляемая справка API)
description: Функция QualifierSet_Next получает следующий квалификатор в перечислении.
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
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174879"
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

`vFunc`(в) Этот параметр не используется.

`ptr`(в) Указатель на экземпляр [IWbemqualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`lFlags`(в) Защищены. Этот параметр должен быть 0.

`pstrName`(ваут) Название квалификатора. Если `null`этот параметр игнорируется; в `pstrName` противном случае, `BSTR` не должны указывать на действительный или утечка памяти происходит. Если не нулевые, функция `BSTR` всегда выделяет `WBEM_S_NO_ERROR`новый, когда он возвращается.

`pVal`(ваут) В случае успеха значение для квалификатора. Если функция выходит `VARIANT` из строя, указанная `pVal` не изменяется. Если этот `null`параметр, параметр игнорируется.

`plFlavor`(ваут) Указатель на LONG, который получает квалификационный вкус. Если информация о вкусе не `null`желательна, этот параметр может быть.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недействительный параметр. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Звонивший не звонил [QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md) |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти доступно для начала нового перечисления. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | В перечислении больше не осталось квалификаторов. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов [IWbemqualifierSet::Следующий](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) метод.

Вы называете функцию `QualifierSet_Next` повторно, чтобы перечислить все `WBEM_S_NO_MORE_DATA`квалификаторы до возвращения функции. Чтобы досрочно завершить перечисление, позвоните [в функцию QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)

Порядок квалификаторов, возвращенных во время перечисления, не определен.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
