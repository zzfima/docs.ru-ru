---
title: "Атрибут mc: Ignorable | Microsoft Docs"
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
  - "mc - префикс пространства имен XML"
  - "mc: Ignorable - атрибут"
  - "mc:ProcessContent - атрибут"
  - "XAML, mc: Ignorable - атрибут"
  - "XAML, mc:ProcessContent - атрибут"
  - "XML, mc - префикс пространства имен"
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Атрибут mc: Ignorable
Задает, какие префиксы пространств имен [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] в файле разметки могут быть проигнорированы процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Атрибут `mc:Ignorable` поддерживает совместимость разметки для пользовательского сопоставления пространства имен и для различных версий [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
## Использование атрибута XAML \(один префикс\)  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## Использование атрибута XAML \(два префикса\)  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|*ignorablePrefix, ignorablePrefix1 и т.д.*|Любая допустимая префиксная строка, в спецификации XML 1.0.|  
|*ignorableUri*|Любой допустимый URI для назначения пространства имен в спецификации XML 1.0.|  
|*ThisElementCanBeIgnored*|Элемент, который может быть проигнорирован реализациями процессора [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], если базовый тип не может быть разрешен.|  
  
## Заметки  
 Префикс пространства имен `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] является рекомендуемым префиксом соглашения для использования при сопоставлении [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] совместимых пространств имен [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].  
  
 Элементы или атрибуты, где префиксная часть имени элемента определяется как `mc:Ignorable`, не создают ошибок при обработке процессором [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Если этот атрибут не может быть разрешен для базового типа или конструкции программирования, то этот элемент игнорируется.  Однако следует обратить внимание на то, что игнорированные элементы могут по\-прежнему создавать дополнительные синтаксические ошибки для дополнительных требований к элементу, так что побочные эффекты этого элемента не обрабатываются.  Например, определенной модели содержимого элемента может потребоваться только один дочерний элемент, но если указанный дочерний элемент был с префиксом `mc:Ignorable` и этот элемент не удалось привести к типу, процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может вызвать ошибку.  
  
 `mc:Ignorable` применяется только для сопоставления пространства имен со строками идентификатора.  `mc:Ignorable` не применяется для сопоставления пространства имен в сборках, указывающих сборку и пространство имен [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] \(или по умолчанию для текущего исполняемого файла в качестве сборки\).  
  
 При реализации процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] не должны создаваться ошибки анализа или выполнения при приведении типа любого элемента или атрибута, которые уточняются префиксом, определенным как `mc:Ignorable`.  Но реализация процессора по\-прежнему может вызывать исключения, которые являются побочным результатом сбоя загрузки или обработки элемента, например данный раннее пример одного дочернего элемента.  
  
 По умолчанию процессор [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] будет игнорировать содержимое внутри игнорируемого элемента.  Однако можно указать дополнительный атрибут [Атрибут mc:ProcessContent](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md) для продолжения обработки содержимого в пределах игнорируемого элемента следующим доступным родительским элементом.  
  
 Множественные префиксы могут быть указаны в атрибуте, используя один или несколько знаков пробела в качестве разделителя, например: `mc:Ignorable="ignore1 ignore2"`.  
  
 Пространство имен [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] определяет другие элементы и атрибуты, не описанные в этой области [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].  Дополнительные сведения содержатся в разделе [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).  
  
## См. также  
 <xref:System.Windows.Markup.XamlReader>   
 [Атрибут PresentationOptions:Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)   
 [Общие сведения о языке XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)