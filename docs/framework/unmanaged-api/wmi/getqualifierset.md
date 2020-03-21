---
title: Функция GetqualifierSet (неуправляемая ссылка на API)
description: Функция GetQualifierSet получает набор квалификаторов для класса или экземпляра.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176777"
---
# <a name="getqualifierset-function"></a>Функция GetQualifierSet
Получает набор квалификатор для экземпляра или определения класса.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a>Параметры

`vFunc`  
(в) Этот параметр не используется.

`ptr`  
(в) Указатель на экземпляр [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`ppQualSet`  
(ваут) Получает указатель интерфейса, позволяющий получить доступ к квалификаторам объекта класса. Параметр `ppQualSet` не может иметь значение `null`. При возникновении ошибки новый объект не возвращается, а указатель остается неизмененным.

## <a name="return-value"></a>Возвращаемое значение

Следующие значения, возвращенные этой функцией, определяются в файле заголовка *WbemCli.h* или вы можете определить их как константы в коде:

|Постоянно  |Значение  |Описание  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Произошел общий сбой. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Указанный метод не существует. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Недостаточно памяти для выполнения операции. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Параметр `null`. |
|`WBEM_S_NO_ERROR` | 0 | Вызов функции был успешным.  |
  
## <a name="remarks"></a>Remarks

Эта функция завершает вызов методом [IWbemClassObject::GetQualifierSet.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)

[Указатель IWbemqualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) позволяет вызывающе добавлять, отсеивать или удалять эти квалификаторы. Такие добавленные, отредактированные или удаленные квалификаторы применяются ко всему определению экземпляра или класса.

## <a name="requirements"></a>Требования  
**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils.idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [WMI и счетчики производительности (справочник по неуправляемым API)](index.md)
