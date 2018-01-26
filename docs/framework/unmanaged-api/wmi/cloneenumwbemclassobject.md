---
title: "Функция CloneEnumWbemClassObject (Справочник по неуправляемым API)"
description: "Функция CloneEnumWbemClassObject делает логическую копию перечислителя."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a>Функция CloneEnumWbemClassObject
Создается копия логического перечислителя, сохраняя его текущую позицию в перечислении.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a>Параметры

`ppEnum`  
[out] Получает указатель на новый [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).

`authLevel`  
[in] Уровень авторизации.

`impLevel`[in] Уровень олицетворения.

`pCurrentEnumWbemClassObject`  
[out] Указатель на [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) экземпляра для клонирования.

`strUser`   
[in] Имя пользователя. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

`strPassword`   
[in] Пароль. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

`strAuthority`   
[in] Имя домена пользователя. В разделе [ConnectServerWmi](connectserverwmi.md) функции для получения дополнительной информации.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращаемые этой функцией, определяются в *WbemCli.h* файла заголовка, или их можно определить как константы в коде:

|Константа  |Значение  |Описание:  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Недопустимый параметр. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Не хватает памяти завершить операцию. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Не удалось выполнить вызов RPC удаленной процедуры связь между текущим процессом и WMI. |
| `WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) метод.

Этот метод копирует только «наилучшим возможным образом». Из-за динамической природы многих объектов CIM возможна новый перечислитель не выполняет перечисление тот же набор объектов, что перечислителя источника.  

При сбое вызова функции, можно получить дополнительные сведения об ошибке, вызвав [GetErrorInfo](geterrorinfo.md) функции.

## <a name="example"></a>Пример

Пример см. в разделе [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
