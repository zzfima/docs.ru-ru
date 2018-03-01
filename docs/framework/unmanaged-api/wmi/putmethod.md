---
title: "Функция PutMethod (Справочник по неуправляемым API)"
description: "Функция PutMethod создает метод."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a>Функция PutMethod
Создает метод.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`  
[in] Указатель на [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) экземпляра.

`wszName`  
[in] Имя метода для создания. 

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pSignatureIn`  
[in] Указатель на копию [__Parameters системный класс](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , содержащий `in` параметры для метода. Этот параметр учитывается, если значение `null`.  

`pSignatureOut`  
[in]  Указатель на копию [__Parameters системный класс](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) , содержащий `out` параметры для метода. Этот параметр учитывается, если значение `null`.
 

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]` Параметра метода, указанного в оба *pInSignature* и *pOutSignature* объекты имеют разные квалификаторы.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Параметр метода отсутствует спецификация **идентификатор** квалификатор. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Ряд идентификатор, присвоенный параметры метода не последовательных или не начинается с 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Возвращаемое значение метода имеет **идентификатор** квалификатор. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Была предпринята попытка повторно использовать существующее имя метода из родительского класса, а не соответствует подписи. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) метод.

Вызов этого метода поддерживается только в том случае, если `ptr` является определение класса CIM. Метод обработки не доступен из [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) указателей, указывающих на экземпляры CIM.

Пользователи не могут создавать методы с именами, начинаться или заканчиваться символом подчеркивания. Данное свойство зарезервировано для системных классов и свойств.

Для метода `in` и `out` параметры описаны как свойства в [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) объектов.

`[in/out]` Параметра можно определить путем добавления и то же свойство для обоих объектов, указываемых `pInSignature` и `pOutSignature` параметров. В этом случае свойства того же **идентификатор** значение квалификатора.

Каждое свойство в [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) класса объекта, отличного от `ReturnValue` должен иметь **идентификатор** квалификатор, отсчитываемый от нуля числовое значение, определяющее порядок, в котором параметры появляются. Нет два параметра может иметь такой же **идентификатор** значение и нет **идентификатор** значение может быть пропущен. Если любое из этих условий `PutMethod` возврата функцией `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Пример

Пример см. в разделе [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
