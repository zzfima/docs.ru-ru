---
title: "Удаление функции (Справочник по неуправляемым API)"
description: "Функция удаления удаляет указанное свойство и все его квалификаторов из определения класса CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Delete
helpviewer_keywords: Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30f5bf651990cafe06811019cf2b3d92f866f646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="delete-function"></a>Удаление функции
Удаляет указанное свойство и все его квалификаторов из определения класса CIM.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszName`  
[in] Имя свойства для удаления. `wszName`должен быть указателем на допустимый `LPCWSTR`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошла неизвестная ошибка. |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | Не удается удалить свойство. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `wszzName` недопустим. |
| `WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не существует. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти для завершения операции. |
| `WBEM_E_PROPAGATED_PROPERTY` | 0x8004101c | Свойство наследуется от базового класса. |
| `WBEM_E_SYSTEM_PROPERTY` | | Свойство системного свойства. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
| `WBEM_E_RESET_TO_DEFAULT` | 0x80041030 | Функция удалить переопределение по умолчанию для текущего класса. Значение по умолчанию для этого свойства в родительском классе был reactiviated. | 

## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
