---
title: "Функция QualifierSet_Next (Справочник по неуправляемым API)"
description: "Функция QualifierSet_Next получает следующий квалификатор в перечислении."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Next
helpviewer_keywords: QualifierSet_Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b66eeab2cba18268b602350c8bc8f489d943309
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetnext-function"></a>Функция QualifierSet_Next
Извлекает следующий квалификатор в перечислении, работы с помощью вызова [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.   

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
[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.

`lFlags`   
[in] Зарезервировано. Этот параметр должен быть 0.

`pstrName`   
[out] Имя квалификатора. Если `null`, этот параметр игнорируется, в противном случае — `pstrName` не должен указывать на допустимый `BSTR` или возникает утечка памяти. Если значение не null, функция всегда выделяет новый `BSTR` Когда возвращается `WBEM_S_NO_ERROR`.

`pVal`   
[out] При успешном выполнении значение квалификатора. Если функция завершается с ошибкой, `VARIANT` , на который указывает `pVal` не изменяется. Если этот параметр равен `null`, что параметр учитывается.

`plFlavor`   
[out] Указатель на значение типа LONG, принимающий флаг квалификатора. Если сведения о версии не требуется, этот параметр может иметь `null`. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Вызывающая сторона не вызвала [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Чтобы начать новое перечисление доступен не хватает памяти. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительные квалификаторы остаются в перечислении. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx) метод.

Можно вызвать `QualifierSet_Next` функции, чтобы перечислить все квалификаторы до возврата функции `WBEM_S_NO_MORE_DATA`. Чтобы завершить перечисление рано, вызовите [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) функции.

Заказ квалификаторов, возвращенного во время перечисления не определено.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
