---
title: Функция ForwardTranslateAccelerator - ссылка на Неуправляемый API WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186621"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Функция ForwardTranslateAccelerator (Ссылка на Неуправляемый API WPF)
Этот API поддерживает инфраструктуру Фонда презентаций Windows (WPF) и не предназначен для использования непосредственно из вашего кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления окнами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Параметры  
 pMsg  
 Указатель на сообщение.  
  
 appUnhandled  
 `true`когда приложению уже была предоставлена возможность обрабатывать входное сообщение, но оно не обрабатывается; в `false`противном случае, .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Смотрите [требования рамочной системы .NET](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 В рамках .NET 3.0 и 3.5: PresentationHostDLL.dll  
  
 В рамках .NET 4 и позже: PresentationHost_v0400.dll  
  
 **Рамочная версия .NET:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
