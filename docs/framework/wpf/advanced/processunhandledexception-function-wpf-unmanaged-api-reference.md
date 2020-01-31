---
title: Функция Процессунхандледексцептион — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743923"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>Функция Процессунхандледексцептион (Справочник по неуправляемым интерфейсам API WPF)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для обработки исключений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>Параметры  
 errorMsg  
 Сообщение об ошибке.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).  
  
 **КОМПОНОВКИ**  
  
 В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll  
  
 В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll  
  
 **Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
