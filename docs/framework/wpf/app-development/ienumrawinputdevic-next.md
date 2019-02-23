---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: a1f76bf42da9a311633de39e42dee2055fac4a27
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745189"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Перечисляет следующие `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) структуры в списке перечислителя, возвращая их в `rgelt` вместе с фактическое число перечисляемых элементов в `pceltFetched`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
  
 [in] Число [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) структур, возвращаемые в `rgelt`.  
  
 `rgelt`  
  
 [out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .  
  
 `pceltFetched`  
  
 [out] Указатель на количество элементов, фактически представленных в `rgelt`. Вызывающий объект может передать `NULL`, если `rgelt` — один.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: Значение S_OK, если число предоставленных элементов является `celt`; В противном случае значение S_FALSE.
