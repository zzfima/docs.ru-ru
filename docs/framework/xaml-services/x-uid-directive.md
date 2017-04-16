---
title: "x:Uid Directive | Microsoft Docs"
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
  - "XAML [XAML Services], localizable content attribute"
  - "XAML [XAML Services], x:Uid attribute"
  - "x:Uid attribute [XAML Services]"
  - "Uid attribute [XAML Services]"
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Uid Directive
Предоставляет уникальный идентификатор для элементов разметки.  Во многих случаях этот уникальный идентификатор используется в процессах и средствах локализации XAML.  
  
## Использование атрибута XAML  
  
```  
<object x:Uid="identifier"... />  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`identifier`|Созданная вручную или сформированная автоматически строка, которая должна быть уникальной в пределах файла при его интерпретации получателем `x:Uid`.|  
  
## Заметки  
 В \[MS\-XAML\] `x:Uid` определяется как директива.  Дополнительные сведения см. в разделе [\[MS\-XAML\] Раздел 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525).  
  
 `x:Uid` обособлен от `x:Name`, как из\-за указанного сценария локализации XAML, и поэтому, что идентификаторы, используемые для локализации, не имеют зависимости от особенностей модели программирования `x:Name`.  Кроме того, `x:Name` управляется областью имен XAML; однако `x:Uid` не управляется никакой определенной в языке XAML концепцией принудительного применения уникальности.  В широком смысле от обработчиков XAML \(обработчики, которые не являются частью процесса локализации\) не ожидается принудительного обеспечения уникальности значений `x:Uid`.  Эту ответственность концептуально несет источник значений.  Требование уникальности значений `x:Uid` внутри одного источника XAML является обоснованным для потребителей значений, таких как выделенные процессы или инструменты глобализации.  Типичная модель уникальности предполагает, что значения `x:Uid` являются уникальными в закодированном XML файле, представляющем XAML.  
  
 Средства, которые обладают значительными знаниями определенной схемы XAML, могут применять `x:Uid` только для истинных локализуемых строк, а не во всех случаях, где значение строки текста встречается в разметке.  
  
 Платформы могут задать конкретное свойство в своей модели объекта как псевдоним для `x:Uid`, применив атрибут <xref:System.Windows.Markup.UidPropertyAttribute> к определяющему типу.  Если платформа определяет конкретное свойство, нельзя указать `x:Uid` и член с псевдонимом в одном объекте.  Если указаны `x:Uid` и член с псевдонимом, API служб XAML платформы .NET Framework в этом случае обычно выдает исключение <xref:System.Xaml.XamlDuplicateMemberException>.  
  
## Примечания об использовании WPF  
 Дополнительные сведения о роли `x:Uid` в процессе локализации WPF и в форме BAML языка XAML см. в разделе [Глобализация для WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md) или <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>  
  
## См. также  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>   
 <xref:Microsoft.Build.Tasks.Windows.UidManager>   
 [Глобализация для WPF](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)