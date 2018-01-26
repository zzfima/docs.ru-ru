---
title: "Get-функция (Справочник по неуправляемым API)"
description: "Функция Get возвращает значение указанного свойства."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Get
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Get
helpviewer_keywords: Get function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69312030689ab1b87e3aadd040395f06e1c94ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="get-function"></a>Функция get
Получает значение указанного свойства, если он существует.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszName`  
[in] Имя свойства.

`lFlags`[in] Зарезервировано. Этот параметр должен быть 0.

`pVal`[out] Если функция возвращает успешно, содержит значение `wszName` свойства. `pval` Аргумент назначен правильный тип и значение квалификатора.

`pvtType`[out] Если функция возвращает успешно, содержит [тип CIM константа](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) , указывающее тип свойства. Его значение может быть также `null`. 

`plFlavor`[out] Если функция возвращает успешно, получает информацию о происхождении свойства. Его значение может быть `null`, или один из следующих WBEM_FLAVOR_TYPE констант, определенных в *WbemCli.h* файл заголовка: 

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является свойством стандартной системы. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: свойство наследуется от родительского класса. </br> Для экземпляра: свойство, пока наследуется от родительского класса, не был изменен в экземпляре.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: свойство принадлежит производного класса. </br> Для экземпляра: свойство изменяется в экземпляре; то есть указано значение или квалификатор была добавлена или изменена. |

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанное свойство не найдено. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для завершения операции. |
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) метод.

`Get` Функция также может возвращать свойства системы.

`pVal` Аргумент назначен правильный тип и значение для квалификатора и COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) функции

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
