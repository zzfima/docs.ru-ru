---
title: "Атрибут mc:ProcessContent | Microsoft Docs"
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
  - "mc:ProcessContent - атрибут"
  - "XAML, mc:ProcessContent - атрибут"
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Атрибут mc:ProcessContent
Указывает элементы [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], которые должны по\-прежнему иметь содержимое, обработанное соответствующими родительскими элементами, даже если непосредственный родительский элемент может быть проигнорирован процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] из\-за указания [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).  Атрибут `mc:ProcessContent` поддерживает совместимость разметки для пользовательского сопоставления пространства имен и для различных версий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## Использование атрибута XAML  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|*ignorablePrefix*|Любая допустимая префиксная строка, в спецификации XML 1.0.|  
|*ignorableUri*|Любой допустимый URI для назначения пространства имен в спецификации XML 1.0.|  
|*ThisElementCanBeIgnored*|Элемент, который может быть проигнорирован реализациями процессора [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], если базовый тип не может быть разрешен.|  
|*\[content\]*|*ThisElementCanBeIgnored*  помечен как игнорируемый.  Если обработчик игнорирует этот элемент, *\[content\]* обрабатывается *объектом*.|  
  
## Заметки  
 По умолчанию процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое внутри игнорируемого элемента.  Можно указать определенный элемент с помощью `mc:ProcessContent`, и процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет продолжать обработку содержимого внутри игнорируемого элемента.  Это обычно будет использоваться, если содержимое вложено в несколько тегов, хотя бы один из которых является игнорируемым и хотя бы один из которых не является игнорируемым.  
  
 В атрибуте могут быть заданы несколько префиксов через пробел, например `mc:ProcessContent="ignore:Element1 ignore:Element2"`.  
  
 Пространство имен [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] определяет другие элементы и атрибуты, не описанные в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].  Дополнительные сведения содержатся в разделе [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## См. также  
 [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)