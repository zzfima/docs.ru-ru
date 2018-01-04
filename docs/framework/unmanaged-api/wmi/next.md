---
title: "Функция Next (Справочник по неуправляемым API)"
description: "Далее функция retireves далее свойства перечисления."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Next
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Next
helpviewer_keywords: Next function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e59ef3f65b75a91708dc65f7d4e3d811dc2d3f9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="next-function"></a>Функция Next
Извлекает свойство next в перечисление, которое начинается с вызова [BeginEnumeration](beginenumeration.md).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
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

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pstrName`  
[out] Новый `BSTR` , содержащий имя свойства. Этот параметр можно задавать `null` Если имя не является обязательным.

`pVal`  
[out] Объект `VARIANT` заполняются значением свойства. Этот параметр можно задавать `null` Если значение не требуется. Если функция возвращает код ошибки `VARIANT` передаваемый `pVal` влево без изменений. 

`pvtType`  
[out] Указатель на `CIMTYPE` переменной ( `LONG` в который помещается тип свойства). Значение этого свойства может быть `VT_NULL_VARIANT`, в этом случае необходимо определить фактический тип свойства. Этот параметр также может быть `null`. 

`plFlavor`  
[out] `null`, или значение, которое получает сведения об источнике свойства. В разделе [Примечание] для возможных значений. 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Был не вызов [ `BeginEnumeration` ](beginenumeration.md) функции. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Чтобы начать новое перечисление доступен не хватает памяти. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Удаленный вызов процедур в диапазоне от текущего процесса и управления Windows не удалось. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Нет дополнительных свойств в перечислении. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::Next](https://msdn.microsoft.com/library/aa391453(v=vs.85).aspx) метод.

Этот метод также возвращает системные свойства.

Если базовый тип свойства является путь к объекту, даты или времени или другой специальный тип, возвращаемый тип не содержит достаточно информации. Вызывающий объект должен проверить `CIMTYPE` для заданного свойства определить, является ли свойство ссылку на объект, даты или времени или другой специальный тип.

Если `plFlavor` не `null`, `LONG` значение получает информацию о происхождении свойства следующим образом:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | Свойство является свойством стандартной системы. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Для класса: свойство наследуется от родительского класса. </br> Для экземпляра: свойство, пока наследуется от родительского класса, не был изменен в экземпляре.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Для класса: свойство принадлежит производного класса. </br> Для экземпляра: свойство изменяется в экземпляре; то есть указано значение или квалификатор была добавлена или изменена. |

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
