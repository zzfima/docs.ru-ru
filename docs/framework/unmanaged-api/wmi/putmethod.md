---
title: Функция PutMethod (Справочник по неуправляемым API)
description: Функция PutMethod создает метод.
ms.date: 11/06/2017
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
ms.openlocfilehash: 99bc65b0181a7c0ab7877273b3747ece91544f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049262"
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
[in] Указатель на [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) экземпляра.

`wszName`  
[in] Имя метода для создания. 

`lFlags`  
[in] Зарезервировано. Этот параметр должен быть 0.

`pSignatureIn`  
[in] Указатель на копию [__Parameters системный класс](/windows/desktop/WmiSdk/--parameters) , содержащий `in` параметры метода. Этот параметр учитывается, если значение `null`.  

`pSignatureOut`  
[in]  Указатель на копию [__Parameters системный класс](/windows/desktop/WmiSdk/--parameters) , содержащий `out` параметры метода. Этот параметр учитывается, если значение `null`.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файл заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Один или несколько параметров недопустимы. |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | 0x80041043 | `[in, out]` Параметра метода, указанных в свойствах *pInSignature* и *pOutSignature* объекты имеют разные квалификаторы.
| `WBEM_E_MISSING_PARAMETER_ID` | 0x80041036 | Параметр метода отсутствует спецификация **идентификатор** квалификатор. |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | 0x80041038 | Серии идентификатор, присвоенный параметры метода не является последовательных или не начинаются с 0. |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | 0x80041039 | Возвращаемое значение метода имеет **идентификатор** квалификатор. |
| `WBEM_E_PROPAGATED_METHOD` | 0x80041034 | Была предпринята попытка повторно использовать существующее имя метода из класса-родителя, а не соответствует подписи. |
| `WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным. |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) метод.

Вызов этого метода поддерживается только в том случае, если `ptr` является определение класса CIM. Метод манипуляции не доступен из [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) указатели, которые указывают на экземпляры CIM.

Пользователи не могут создавать методы с именами, начинаться или заканчиваться символом подчеркивания. Этот атрибут зарезервирован для системных классов и свойств.

Для метода `in` и `out` параметры описаны в виде свойств [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) объектов.

`[in/out]` Параметра можно определить путем добавления одного свойства обоих объектов, указываемых `pInSignature` и `pOutSignature` параметров. В этом случае свойства одного и того же **идентификатор** значение квалификатора.

Каждое свойство в [__Parameters](/windows/desktop/WmiSdk/--parameters) класса объектов, отличных от `ReturnValue` должен иметь **идентификатор** квалификатор, отсчитываемый от нуля числовое значение, определяющее порядок, в котором параметры появляются. Нет два параметра могут иметь такой же **идентификатор** значения и **идентификатор** значение может быть пропущен. Если любое из этих условий, `PutMethod` возвращает `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.

## <a name="example"></a>Пример

Например, см. в разделе [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым API)](index.md)
