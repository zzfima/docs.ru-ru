---
title: Функция Креатеидиспатчстафорвардер — Справочник по неуправляемым API в WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738030"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Функция Креатеидиспатчстафорвардер (Справочник по неуправляемым интерфейсам API WPF)
Этот API поддерживает инфраструктуру Windows Presentation Foundation (WPF) и не предназначен для непосредственного использования из кода.  
  
 Используется инфраструктурой Windows Presentation Foundation (WPF) для управления потоками и окнами.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Параметры  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 пдиспатчделегате  
 Указатель на интерфейс `IDispatch`.  
  
 ппфорвардер  
 Указатель на адрес интерфейса `IDispatch`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. [.NET Framework требования к системе](../../get-started/system-requirements.md).  
  
 **КОМПОНОВКИ**  
  
 В .NET Framework 3,0 и 3,5: Пресентатионхостдлл. dll  
  
 В .NET Framework 4 и более поздних версиях: PresentationHost_v0400. dll  
  
 **Версия .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Справочник по неуправляемым API WPF](wpf-unmanaged-api-reference.md)
