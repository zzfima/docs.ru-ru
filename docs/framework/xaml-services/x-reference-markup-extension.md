---
title: "x:Reference Markup Extension | Microsoft Docs"
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
  - "x:Reference markup extension [XAML Services]"
  - "XAML [XAML Services], x:Reference Markup Extension"
  - "Reference markup extension [XAML Services]"
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:Reference Markup Extension
Ссылается на экземпляр, который объявлен в другом месте в разметке XAML.  Ссылка на `x:Name` элемента.  
  
## Использование атрибута XAML  
  
```  
<object property="{x:Reference instancexName}" .../>  
```  
  
## Использование элемента объекта XAML  
  
```  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`instancexName`|Значение `x:Name` \(или значение свойства, определяемого <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>\) экземпляра, на который указывает ссылка.|  
  
## Заметки  
 `x:Reference` обеспечивает поддержку уровня языка XAML для концепции ссылки элемента, которая в определенных платформах была реализована иначе, например в WPF.  
  
## x:Reference и WPF  
 В WPF и XAML 2006 ссылки элемента реализуются функцией уровня среды привязки <xref:System.Windows.Data.Binding.ElementName%2A>.  Для большинства приложений и сценариев WPF по\-прежнему необходимо использовать привязку <xref:System.Windows.Data.Binding.ElementName%2A>.  Исключениями из этого общего правила могут быть случаи, в которых контекст данных или другие соображения делают привязку данных непрактичной, и случаи, когда не включена компиляция разметки.  
  
 `x:Reference` — это конструкция, определенная в XAML 2009.  В WPF можно использовать возможности XAML 2009, но только для кода XAML, который не является компилированной разметкой WPF.  XAML с компилированной разметкой и форма BAML языка XAML в настоящее время не поддерживают ключевые слова и функции языка XAML 2009.