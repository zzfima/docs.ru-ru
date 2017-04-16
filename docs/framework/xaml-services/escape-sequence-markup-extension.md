---
title: "{} Escape Sequence / Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "{}"
helpviewer_keywords: 
  - "XAML [XAML Services], quotation mark (")"
  - "{} escape sequence [XAML Services]"
  - "XAML [XAML Services], {} escape sequence"
  - "XAML [XAML Services], escape sequence"
  - "quotation mark (") [XAML Services]"
  - "escape sequence [XAML Services]"
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: 21
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
---
# {} Escape Sequence / Markup Extension
Предоставляет escape\-последовательность XAML для значений атрибутов.  escape\-последовательность XAML позволяя последующим значениям в атрибуте интерпретироваться в качестве литералов.  
  
## Использование атрибута XAML  
  
```  
<object property="{} literalValue" .../>  
```  
  
## Использование элемента свойства XAML  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|*literalValue*|Символьная строка, которая следует за escape\-последовательность.  Как правило, эта строка содержит открывающую или закрывающую скобку \({ или }\).|  
  
## Заметки  
 Escape\-последовательность \({}\) используется таким образом, чтобы открывающая фигурная скобка \({\) можно было использовать в качестве знака литерала в XAML.  
  
 Средства чтения XAML обычно используют открывающие фигурные скобки \({\) для обозначения точки входа расширения разметки. Однако они сначала проверяют следующий символ, чтобы определить, является ли это закрывающей фигурной скобкой \(}\).  Только тогда, когда две фигурные скобки \({}\) являются смежными, они считаются escape\-последовательностью.  
  
 При обнаружении escape\-последовательности средство чтения XAML должно обработать остаток строки как строку.  Однако если escape\-последовательность применяется к члену, имеющему преобразователь типов, возможно, при интерпретации строки средством записи XAML будет выполнено преобразование типа.  
  
 escape\-последовательность не является расширением разметки и не поддерживается классом.  Однако это соглашение должны учитывать средства чтения XAML \(в том числе пользовательские средства чтения XAML\).  
  
 Знак кавычки \(''\) не может использоваться как escape\-последовательность подобным образом.  Если необходимо задать знак кавычек в качестве значения для свойства, не являющегося содержимым, используйте синтаксис элемента свойства и поместите знак кавычки в виде строки внутри элемента свойства или используйте сущность символов XML.  Для свойства содержимого знак кавычек может быть всем содержимым.  
  
 Escape\-последовательность \({}\) часто требуется при указании типа XML, который должен включать квалификатор пространства имен в том месте, где должно отображаться расширение разметки XAML.  Включает начало значения атрибута XAML и в расширении разметки следует сразу после знака равенства \(\=\).  В следующем примере показаны escape\-последовательности для пространства имен XML, которые отображаются в начале значения атрибута XAML.  
  
 [!code-xml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## См. также  
 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)   
 [XML Character Entities and XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)