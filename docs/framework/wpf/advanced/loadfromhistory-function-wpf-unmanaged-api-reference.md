---
title: Функция Лоадфромхистори — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727930"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Функция Лоадфромхистори (Справочник по неуправляемым интерфейсам API WPF)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Параметры  
 фистористреам  
 Указатель на поток данных журнала.  
  
 пбиндкткс  
 Указатель на контекст привязки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).  
  
 **КОМПОНОВКИ**  
  
 В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll  
  
 В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll  
  
 **Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
