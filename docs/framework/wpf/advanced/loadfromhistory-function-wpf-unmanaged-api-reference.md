---
title: Функция LoadFromHistory (WPF Справочник по неуправляемым API)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 155b83b8b904350bd6faf73ea21d1db4f83085b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376134"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Функция LoadFromHistory (WPF Справочник по неуправляемым API)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для использования непосредственно из программного кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a>Параметры  
 pHistoryStream  
 Указатель на поток данных предыстории.  
  
 pBindCtx  
 Указатель на контекст привязки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. в разделе [системные требования .NET Framework](../../get-started/system-requirements.md).  
  
 **БИБЛИОТЕКА DLL:**  
  
 В .NET Framework 3.0 и 3.5: PresentationHostDLL.dll  
  
 В .NET Framework 4 и более поздних версий: PresentationHost_v0400.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
