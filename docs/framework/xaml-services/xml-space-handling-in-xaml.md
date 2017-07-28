---
title: "xml:space Handling in XAML | Microsoft Docs"
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
  - "XAML [XAML Services], xml:space attribute"
  - "XAML [XAML Services], whitespace processing"
  - "xml:space attribute [XAML Services]"
  - "whitespace processing [XAML Services]"
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 15
---
# xml:space Handling in XAML
Атрибут `xml:space` является атрибутом, определенным в XML, который объявляет поведение обработки значимых пробелов внутри элемента объекта.  Это поведение относится ко всему содержимому \(внутреннему тексту\) элемента, где объявлен `xml:space`, и распространяется на дочерние элементы.  
  
## Использование атрибута XAML  
  
```  
<object xml:space="preserve" />  
```  
  
 \- или \-  
  
```  
<object xml:space="default" />  
```  
  
## Заметки  
 Определение атрибута `xml:space` в XAML, включая два возможных значения, является производным от `xml:space`, определенного как "специальный атрибут" спецификациями W3C для XML.  
  
 По умолчанию значение атрибута `xml:space` является буквенным значением `"default"`.   Если задано значение `"default"` или если `xml:space` не указывается вообще, разбор значащих пробелов выполняется по умолчанию, как определено в разделе [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
 Чтобы сохранить пробелы в содержимом элемента объекта, укажите `xml:space="preserve"` для этого элемента.  
  
 В большинстве интерпретаций действие атрибута `xml:space` и его значение распространяются и на дочерние элементы.  
  
 Полное описание обработки пробелов в XAML см. в разделе [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).  
  
## См. также  
 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)