---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053401"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Перечисляет следующие `celt` структуры [равинпутдевице](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) в списке перечислителя, возвращая их в `rgelt` вместе с фактическим числом перечисляемых элементов в. `pceltFetched`  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>Параметры  
 `celt`  
  
 окне Число структур [равинпутдевице](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) , возвращаемых `rgelt`в.  
  
 `rgelt`  
  
 [out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .  
  
 `pceltFetched`  
  
 [out] Указатель на количество элементов, фактически представленных в `rgelt`. Вызывающий объект может передать `NULL`, если `rgelt` — один.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: S_OK, если число представленных элементов равно `celt`; S_FALSE в противном случае.
