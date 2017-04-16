---
title: "IEnumRAWINPUTDEVIC:Clone | Microsoft Docs"
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
  - "Clone - метод"
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Clone
Создает другой перечислитель необработанного устройства ввода с таким же состоянием, как у текущего перечислителя для прохода по одному и тому же списку.  
  
## Синтаксис  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### Параметры  
 `ppenum`  
  
 \[out\] Адрес выходной переменной, которая получает указатель интерфейса [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md).  Если метод завершается неудачно, значение этой выходной переменной не определено.  
  
## Значение свойства или возвращаемое значение  
 HRESULT: Этот метод поддерживает стандартные возвращаемые значения E\_INVALIDARG, E\_OUTOFMEMORY и E\_UNEXPECTED.  
  
## Заметки  
 Этот метод дает возможность записать позицию в последовательность перечисления для возврата к этой позиции позже.  Вызывающий объект должен освободить этот новый перечислитель отдельно от первого перечислителя.