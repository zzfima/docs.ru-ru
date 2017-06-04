---
title: "Атрибуты в элементах управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "атрибуты [Windows Forms]"
  - "атрибуты [Windows Forms], классы"
  - "атрибуты [Windows Forms], свойства элемента управления"
  - "атрибуты [Windows Forms], свойства привязки данных"
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Атрибуты в элементах управления Windows Forms
В библиотеке .NET Framework содержатся различные атрибуты, которые можно применять к членам собственных элементов управления и компонентам.  Некоторые из этих атрибутов влияют на поведение класса во время выполнения, в то время как другие определяют поведение во время разработки.  
  
## Атрибуты свойств элемента управления и компонента  
 В следующей таблице содержатся атрибуты, которые можно применять к свойствам или другим членам собственных элементов управления и компонентов.  Пример использования большинства из этих атрибутов см. в разделе [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).  
  
|Атрибут|Описание|  
|-------------|--------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Задает значение, которое нужно передать свойству, чтобы это свойство получило значение из другого источника.  Это называется *окружением*.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Указывает, следует ли отображать свойство или событие в окне **Свойства**.|  
|<xref:System.ComponentModel.CategoryAttribute>|Задает имя категории, в которой при отображении в элементе управления <xref:System.Windows.Forms.PropertyGrid> для группировки свойства или события устанавливается режим <xref:System.Windows.Forms.PropertySort>.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Задает для свойства значение по умолчанию.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Задает описание свойства или события.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Задает отображаемое имя для свойства, события или метода `public` `void`, не принимающего аргументов.|  
|<xref:System.ComponentModel.EditorAttribute>|Задает редактор, используемый для изменения свойства.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Указывает на то, что свойство или метод отображаются в редакторе.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Указывает зарезервированное ключевое слово контекста для класса или элемента.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Определяет, должно ли быть локализовано свойство.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Показывает, что текстовое представление объекта скрывается такими символами, как звездочка.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Указывает, доступно ли свойство, с которым связан данный атрибут, только для чтения или для чтения и записи во время разработки.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Показывает, что следует обновить таблицу свойств, когда изменяется значение связанного свойства.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Указывает, какой тип использовать в качестве преобразователя для объекта, с которым связан этот атрибут.|  
  
## Атрибуты для свойств привязки данных  
 В следующей таблице содержатся атрибуты, которые можно применять для определения способа взаимодействия собственных элементов управления и компонентов с привязкой данных.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|<xref:System.ComponentModel.BindableAttribute>|Указывает, предназначено ли свойство для привязки данных.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Указывает свойства источника данных и члена данных для компонента.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Задает для компонента свойство привязки по умолчанию.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Указывает свойства источника данных и члена данных для компонента.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Включает перенаправление атрибутов.|  
  
## Атрибуты для классов  
 В следующей таблице содержатся атрибуты, которые можно применять для определения поведения взаимодействия собственных элементов управления и компонентов во время разработки.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Задает для компонента событие по умолчанию.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Задает для компонента свойство по умолчанию.|  
|<xref:System.ComponentModel.DesignerAttribute>|Задает класс, используемый для реализации служб времени разработки для компонента.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Указывает, что конструктор для класса принадлежит к определенной категории.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Представляет атрибут элемента панели элемента.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Задает строку фильтра и тип фильтра для использования в качестве элемента панели инструментов.|  
  
## См. также  
 <xref:System.Attribute>   
 [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)   
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)