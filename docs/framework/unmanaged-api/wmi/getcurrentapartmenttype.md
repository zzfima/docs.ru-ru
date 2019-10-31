---
title: Функция Жеткуррентапартменттипе (Справочник по неуправляемым API)
description: Функция Жеткуррентапартменттипе Извлекает тип подразделения, в котором выполняется вызывающий объект.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ecd2b49d6850a8fae25ddca54f855fdda2ccabb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120356"
---
# <a name="getcurrentapartmenttype-function"></a>Функция Жеткуррентапартменттипе
Получает тип подразделения, в котором выполняется вызывающий объект.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Параметры

`vFunc`  
окне Этот параметр не используется.

`ptr`  
окне Указатель на экземпляр [икомсреадингинфо](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .

`aptType`  
заполняет Указатель на значение перечисления [апттипе](/windows/win32/api/objidlbase/ne-objidlbase-apttype) , указывающее подразделение вызывающего объекта.

## <a name="return-value"></a>Возвращаемое значение

|Константа  |значения  |Описание  |
|---------|---------|---------|
| `S_OK` | 0 | Функция успешно завершена. |
| `E_FAIL` | 0x80000008 | Вызывающий объект не выполняется в апартаменте. |
  
## <a name="remarks"></a>Заметки

Эта функция заключает в оболочку вызов метода [икомсреадингинфо:: жеткуррентапартменттипе](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .

## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** WMINet_Utils. idl  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>См. также

- [WMI и счетчики производительности (Справочник по неуправляемым интерфейсам API)](index.md)
