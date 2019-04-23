---
title: Функция GetObjectText (Справочник по неуправляемым API)
description: Функция GetObjectText возвращает текстовое отображение объекта на синтаксисе MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208323"
---
# <a name="getobjecttext-function"></a>Функция GetObjectText
Возвращает текстовое отображение объекта в синтаксисе формата управляемых объектов (MOF).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`lFlags`  
[in] Обычно 0. Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указывается, квалификаторы включаются без распространения или flavor информации.

`pstrObjectText`   
[out] Указатель на `null` на запись. Возвращенное значение во вновь выделенный `BSTR` , содержащий синтаксис MOF для преобразования объекта.  

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) метод.

Текст MOF, возвращаемый не содержит все сведения об объекте, но только достаточно информации для компилятора MOF иметь возможность повторного создания исходного объекта. Например включены не распространяются квалификаторы или свойства родительского класса.

Для воссоздания текст параметра метода используется следующий алгоритм:

1. Параметры являются resequenced в порядке их значения идентификатора.
1. Параметры, которые задаются в виде `[in]` и `[out]` объединяются в один параметр.
 
`pstrObjectText` должен быть указателем на `null` при вызове функции; оно не должно указывать на строку, которая является допустимым до вызова метода, поскольку указатель не быть освобождена.

## <a name="requirements"></a>Требования  
**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
