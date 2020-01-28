---
title: Функция Форвардтранслатеакцелератор — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747037"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Функция Форвардтранслатеакцелератор (Справочник по неуправляемым интерфейсам API WPF)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Параметры  
 пмсг  
 Указатель на сообщение.  
  
 аппунхандлед  
 `true`, когда приложению уже предоставлен шанс обработать входное сообщение, но оно не обработано. в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).  
  
 **КОМПОНОВКИ**  
  
 В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll  
  
 В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll  
  
 **Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
