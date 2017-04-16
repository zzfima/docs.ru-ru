---
title: "Атрибут PresentationOptions:Freeze | Microsoft Docs"
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
  - "элементы Freezable"
  - "Freeze - атрибут"
  - "префикс PresentationOptions"
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Атрибут PresentationOptions:Freeze
Устанавливает состояние <xref:System.Windows.Freezable.IsFrozen%2A> в `true` в содержащемся элементе<xref:System.Windows.Freezable>.  Поведение по умолчанию для <xref:System.Windows.Freezable> без указанного атрибута `PresentationOptions:Freeze`, при котором во время загрузки <xref:System.Windows.Freezable.IsFrozen%2A> равно `false` и зависит от общего поведения <xref:System.Windows.Freezable> во время выполнения.  
  
## Использование атрибута XAML  
  
```  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`PresentationOptions`|Префикс пространства имен XML, который может быть любой допустимой префиксной строкой, по спецификации XML 1.0.  Префикс `PresentationOptions` используется для идентификационных целей в этой документации.|  
|`freezableElement`|Элемент, который создает любой производный класс <xref:System.Windows.Freezable>.|  
  
## Заметки  
 Атрибут `Freeze` может быть только атрибутом или другим программируемым элементом, определенным в пространстве имен XML `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.  Атрибут `Freeze` существует в этом специальном пространстве имен, поэтому он может быть назначен в качестве игнорируемого, используя [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) в качестве части объявлений корневого элемента.  Причина, по которой `Freeze` должен иметь возможность быть игнорируемым, в том, что не все реализации процессора [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] способны заморозить <xref:System.Windows.Freezable> во время загрузки; эта возможность не является частью спецификации [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 Возможность обработки атрибута `Freeze` специально строится в процессоре [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], который обрабатывает [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для компилируемых приложений.  Атрибут не является поддерживаемым каким\-либо классом, и синтаксис атрибута не является расширяемым или модифицируемым.  Если вы реализовываете собственный [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессор, вы можете выбрать распараллелить поведение при заморозке процессора [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] при обработке атрибута `Freeze` в элементах <xref:System.Windows.Freezable> во время загрузки.  
  
 Любое значение для атрибута `Freeze`, отличное от `true` \(без учета регистра\), вызовет ошибку во время загрузки.  \(Указание атрибута `Freeze` как `false` не является ошибкой, но он уже имеет такое значение по умолчанию, поэтому параметр `false` не дает никакого эффекта\).  
  
## См. также  
 <xref:System.Windows.Freezable>   
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Атрибут mc: Ignorable](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)