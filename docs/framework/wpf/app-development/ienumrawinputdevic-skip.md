---
title: "IEnumRAWINPUTDEVIC:SKIP | Microsoft Docs"
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
  - "Skip - метод"
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:SKIP
Указывает перечислителю пропустить следующие элементы `celt` в перечислении, чтобы следующий вызов [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) не возвратил эти элементы.  
  
## Синтаксис  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### Параметры  
 `celt`  
  
 \[in\] номера элементов, которые нужно пропустить.  
  
## Значение свойства или возвращаемое значение  
 HRESULT: S\_OK, если количество предоставленных элементов равно `celt`; S\_FALSE в противном случае.