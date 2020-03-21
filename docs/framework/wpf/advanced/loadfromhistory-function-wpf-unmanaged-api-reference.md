---
title: Функция LoadFromHistory - Ссылка на Неуправляемый API WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141579"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Функция LoadFromHistory (Ссылка на Неуправляемый API WPF)
Этот API поддерживает инфраструктуру Фонда презентаций Windows (WPF) и не предназначен для использования непосредственно из вашего кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления окнами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Параметры  
 pHistoryStream  
 Указатель на поток информации об истории.  
  
 pBindCtx  
 Указатель на контекст связывания.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Смотрите [требования рамочной системы .NET](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 В рамках .NET 3.0 и 3.5: PresentationHostDLL.dll  
  
 В рамках .NET 4 и позже: PresentationHost_v0400.dll  
  
 **Рамочная версия .NET:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
