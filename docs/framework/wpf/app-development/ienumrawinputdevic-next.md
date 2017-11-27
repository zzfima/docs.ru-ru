---
title: IEnumRAWINPUTDEVIC:Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 644a8e724a280a8b23048a381a099acd6e655d2c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Перечисляет следующего `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) структуры в списке перечислителя, возвращая их в `rgelt` вместе с фактическое число перечисленных элементов в `pceltFetched`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Параметры  
 `celt`  
  
 [in] Число [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) структур, возвращаемые в `rgelt`.  
  
 `rgelt`  
  
 [out] Массив celt размера (или больше) для получения перечисленных структур RAWINPUTDEVICE .  
  
 `pceltFetched`  
  
 [out] Указатель на количество элементов, фактически представленных в `rgelt`. Вызывающий объект может передать `NULL`, если `rgelt` — один.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: значение S_OK, если число предоставленных элементов составляет `celt`; в противном случае значение S_FALSE.
