---
title: "Функция GetMethodOrigin (Справочник по неуправляемым API)"
description: "Функция GetMethodOrigin определяет класс, в котором объявлен метод."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethodOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethodOrigin
helpviewer_keywords: GetMethodOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7982ef2f272173e89434b64a4c296a2ce963594e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2017
---
# <a name="getmethodorigin-function"></a>Функция GetMethodOrigin
Определяет класс, в котором объявлен метод.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszMethodName`  
[in] Имя метода для объекта, владеющего класс которого запрашивается. 

`pstrClassName`  
[out] Получает имя класса, которому принадлежит метод.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не найден. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) метод.

Поскольку класс может наследовать методы из одного или нескольких базовых классов, разработчики часто требуется определить класс, в котором определен данный метод.

`pstrClassName` Параметр не должен указывать на допустимый `BSTR` перед вызовом функции, так как это `out` параметр; этот указатель не освобождается после возвращения функции.

## <a name="requirements"></a>Требования  
**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
