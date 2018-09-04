---
title: Функция QualifierSet_Next (Справочник по неуправляемым API)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 938044a4e932139eb8a4d0a5d2f998cbc6f193cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507697"
---
# <a name="qualifiersetnext-function"></a>Функция QualifierSet_Next
Получает следующий квалификатор в перечислении, начатом вызовом функции [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) экземпляра.

`lFlags`   
[in] Зарезервировано. Этот параметр должен быть 0.

`pstrName`   
[out] Имя квалификатора. Если `null`, этот параметр не учитывается, в противном случае — значение `pstrName` не должна указывать на допустимый `BSTR` или возникает утечка памяти. Если не равно null, функция всегда назначает новый `BSTR` при возврате `WBEM_S_NO_ERROR`.

`pVal`   
[out] При успешном выполнении значение для квалификатора. Если функция завершается с ошибкой, `VARIANT` , на которые указывают `pVal` не изменяется. Если этот параметр имеет `null`, параметр учитывается.

`plFlavor`   
[out] Указатель на значение типа LONG, принимающий флаг квалификатора. Если сведения о версии не требуется, этот параметр может быть `null`. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Вызывающая сторона не вызвала [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти, позволяющих начать новое перечисление. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительные квалификаторы, остаются в перечислении. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) метод.

Вы вызываете `QualifierSet_Next` функции несколько раз, чтобы перечислить все квалификаторы до возврата функции `WBEM_S_NO_MORE_DATA`. Чтобы завершить перечисление раньше, вызовите [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) функции.

Порядок квалификаторы, возвращаемых во время перечисления не определено.

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
