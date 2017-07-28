---
title: "IEnumRAWINPUTDEVIC:Next | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Метод Next"
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# IEnumRAWINPUTDEVIC:Next
Перечисляет следующие структуры `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) в списке перечислителя, возвращая их в `rgelt` наряду с фактическим числом перечисленных элементов в `pceltFetched`.  
  
## Синтаксис  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### Параметры  
 `celt`  
  
 \[in\] Число структур [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp), возвращаемых в `rgelt`.  
  
 `rgelt`  
  
 \[out\] Массив celt размера \(или больше\) для получения перечисленных структур RAWINPUTDEVICE .  
  
 `pceltFetched`  
  
 \[out\] Указатель на количество элементов, фактически представленных в `rgelt`.  Вызывающий объект может передать `NULL`, если `rgelt` — один.  
  
## Значение свойства, возвращаемое значение  
 HRESULT: значение S\_OK, если число предоставленных элементов составляет `celt`; в противном случае значение S\_FALSE.