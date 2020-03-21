---
title: Функция CreateIDispatchSTAForwarder - ссылка на Неуправляемый API WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174723"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Функция CreateIDispatchSTAForwarder (Ссылка на Неуправляемый API WPF)
Этот API поддерживает инфраструктуру Фонда презентаций Windows (WPF) и не предназначен для использования непосредственно из вашего кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоками и окнами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Параметры  
  
## <a name="property-valuereturn-value"></a>Значение свойства/возвращаемое значение  
 pDispatchДелегат  
 Указатель на `IDispatch` интерфейс.  
  
 ppForwarder  
 Указатель на адрес интерфейса. `IDispatch`  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Смотрите [требования рамочной системы .NET](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 В рамках .NET 3.0 и 3.5: PresentationHostDLL.dll  
  
 В рамках .NET 4 и позже: PresentationHost_v0400.dll  
  
 **Рамочная версия .NET:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
