---
title: "Функция GetObjectText (Справочник по неуправляемым API)"
description: "Функция GetObjectText возвращает текстовое отображение объекта на синтаксис MOF."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 27e25a7ab7131f5b1c995c9367de6fe5a6fae592
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="getobjecttext-function"></a>Функция GetObjectText
Возвращает текстовое преобразования объекта в синтаксисе формата управляемых объектов (MOF).

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
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`lFlags`  
[in] Обычно 0. Если `WBEM_FLAG_NO_FLAVORS` (или 0x1) указан, включаются квалификаторы без сведений о распространении или версия.

`pstrObjectText`   
[out] Указатель на `null` на запись. Возвращенное значение вновь выделенный `BSTR` , содержащий синтаксис MOF для преобразования объекта.  

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр не является допустимым. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) метод.

MOF-текст, возвращаемый не содержит все сведения об объекте, но только достаточно сведений для MOF-компилятору иметь возможность повторного создания исходного объекта. Например включаются не распространенный квалификаторы или свойства родительского класса.

Для реконструкции текст параметрам метода используется следующий алгоритм:

1. Параметры являются resequenced в порядке их значения идентификатора.
1. Параметры, которые задаются в виде `[in]` и `[out]` объединяются в один параметр.
 
`pstrObjectText`должен быть указателем на `null` при вызове функции; оно не должно указывать строку, которая является допустимым до вызова метода, поскольку указатель не будет освобождена.

## <a name="requirements"></a>Требования  
**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
