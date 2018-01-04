---
title: "Функция QualifierSet_EndEnumeration (Справочник по неуправляемым API)"
description: "Функция QualifierSet_EndEnumeration завершает перечисления."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d8e6bb24eb471d807af2493f82b6be4f644124f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetendenumeration-function"></a>Функция QualifierSet_EndEnumeration
Завершается перечисление начался вызовом [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) функции.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
[in] Этот параметр не используется.

`ptr`   
[in] Указатель на [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) экземпляра.

## <a name="return-value"></a>Возвращаемое значение

Следующее значение, возвращаемое этой функцией, определенные в *WbemCli.h* файла заголовка, или можно задавать как константа в коде:

|Константа  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | Успешный вызов функции.  |
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) метод.

Этот вызов рекомендуется, но не является обязательным. Он немедленно освобождает ресурсы, связанные с перечислением.

## <a name="requirements"></a>Требования  

**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
**Заголовок:** WMINet_Utils.idl  
  
**Версии платформы .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
