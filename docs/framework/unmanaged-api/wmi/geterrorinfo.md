---
title: Функция GetErrorInfo (Справочник по неуправляемым API)
description: Функция GetErrorInfo извлекает сведения об ошибках в предыдущем вызове функции.
ms.date: 11/06/2017
api_name:
- GetErrorInfo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetErrorInfo
helpviewer_keywords:
- GetErrorInfo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef52a4e503597e08eae407571f02bf63adafc4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455963"
---
# <a name="geterrorinfo-function"></a>GetErrorInfo-функция
Извлекает сведения об ошибках в предыдущем вызове функции.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a>Возвращаемое значение

Указатель на [IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx) объекта после успешного вызова функции, или `null` в случае неудачи.
  
## <a name="remarks"></a>Примечания

Эта функция создает оболочку для вызова [IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) метод.

## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.def  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также  
[WMI и счетчиков производительности (Справочник по неуправляемым API)](index.md)
