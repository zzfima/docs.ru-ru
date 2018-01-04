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
ms.workload: dotnet
ms.openlocfilehash: af6cb5bfe07923e13f1b76c785d830a9af15eaf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
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
