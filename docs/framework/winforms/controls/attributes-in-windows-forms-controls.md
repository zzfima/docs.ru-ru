---
title: Атрибуты в элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- attributes [Windows Forms]
- attributes [Windows Forms], data binding properties
- attributes [Windows Forms], control properties
- attributes [Windows Forms], classes
ms.assetid: 2c5640e9-6c6c-49d7-a5e4-a768f6be7853
ms.openlocfilehash: b32e4f87e953438a3bb11569445a9270e11c7922
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732125"
---
# <a name="attributes-in-windows-forms-controls"></a>Атрибуты в элементах управления Windows Forms
.NET Framework предоставляет широкий набор атрибутов, которые можно применять к членам пользовательских элементов управления и компонентов. Некоторые из этих атрибутов влияют на поведение класса во время выполнения, а другие – на поведение во время разработки.  
  
## <a name="attributes-for-control-and-component-properties"></a>Атрибуты для свойств элементов управления и компонентов  
 В следующей таблице представлены атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов. Пример использования этих атрибутов см. в разделе [Практическое руководство. Применение атрибутов в элементах управления Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md).  
  
|attribute|Description|  
|---------------|-----------------|  
|<xref:System.ComponentModel.AmbientValueAttribute>|Указывает значение, которое нужно передать в свойство, чтобы свойство получило свое значение из другого источника. Это называется *окружением*.|  
|<xref:System.ComponentModel.BrowsableAttribute>|Указывает, должно ли отображаться свойство в окне **Свойства**.|  
|<xref:System.ComponentModel.CategoryAttribute>|Указывает имя категории, в которой будет группироваться свойство или событие, отображаемое в элементе управления <xref:System.Windows.Forms.PropertyGrid>, установленном в режим <xref:System.Windows.Forms.PropertySort.Categorized>.|  
|<xref:System.ComponentModel.DefaultValueAttribute>|Указывает значение свойства по умолчанию.|  
|<xref:System.ComponentModel.DescriptionAttribute>|Задает описание для свойства или события.|  
|<xref:System.ComponentModel.DisplayNameAttribute>|Указывает отображаемое имя для свойства, события или метода `public void`, у которого нет аргументов.|  
|<xref:System.ComponentModel.EditorAttribute>|Указывает редактор, используемый для изменения свойства.|  
|<xref:System.ComponentModel.EditorBrowsableAttribute>|Указывает, что свойство или метод можно просматривать в редакторе.|  
|<xref:System.ComponentModel.Design.HelpKeywordAttribute>|Указывает ключевое слово контекста для класса или элемента.|  
|<xref:System.ComponentModel.LocalizableAttribute>|Указывает, должно ли быть локализовано свойство.|  
|<xref:System.ComponentModel.PasswordPropertyTextAttribute>|Указывает, что текстовое представление объекта скрыто символами, например звездочками.|  
|<xref:System.ComponentModel.ReadOnlyAttribute>|Указывает, предназначено ли свойство, к которому привязан этот атрибут, только для чтения или для чтения и записи во время разработки.|  
|<xref:System.ComponentModel.RefreshPropertiesAttribute>|Указывает, что таблица свойств должна обновляться при изменении значения связанного свойства.|  
|<xref:System.ComponentModel.TypeConverterAttribute>|Указывает, какой тип использовать в качестве преобразователя для объекта, с которым связан этот атрибут.|  
  
## <a name="attributes-for-data-binding-properties"></a>Атрибуты для свойств привязки данных  
 В следующей таблице представлены атрибуты, с помощью которых можно указывать, как пользовательские элементы управления и компоненты взаимодействуют с привязкой данных.  
  
|attribute|Description|  
|---------------|-----------------|  
|<xref:System.ComponentModel.BindableAttribute>|Указывает, используется ли обычно свойство для привязки.|  
|<xref:System.ComponentModel.ComplexBindingPropertiesAttribute>|Указывает источник данных и свойства элемента данных для компонента.|  
|<xref:System.ComponentModel.DefaultBindingPropertyAttribute>|Задает свойство привязки по умолчанию для компонента.|  
|<xref:System.ComponentModel.LookupBindingPropertiesAttribute>|Указывает источник данных и свойства элемента данных для компонента.|  
|<xref:System.ComponentModel.AttributeProviderAttribute>|Включает перенаправление атрибутов.|  
  
## <a name="attributes-for-classes"></a>Атрибуты для классов  
 В следующей таблице представлены атрибуты, с помощью которых можно указать поведение пользовательских элементов управления и компонентов во время разработки.  
  
|attribute|Description|  
|---------------|-----------------|  
|<xref:System.ComponentModel.DefaultEventAttribute>|Задает событие по умолчанию для компонента.|  
|<xref:System.ComponentModel.DefaultPropertyAttribute>|Задает свойство по умолчанию для компонента.|  
|<xref:System.ComponentModel.DesignerAttribute>|Указывает класс, используемый для реализации служб времени разработки для компонента.|  
|<xref:System.ComponentModel.DesignerCategoryAttribute>|Указывает, что конструктор для класса относится к определенной категории.|  
|<xref:System.ComponentModel.ToolboxItemAttribute>|Представляет атрибут элемента панели инструментов.|  
|<xref:System.ComponentModel.ToolboxItemFilterAttribute>|Задает строку фильтра и тип фильтра для элемента панели инструментов.|  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Attribute>
- [Практическое руководство. Применение атрибутов к элементам управления Windows Forms](how-to-apply-attributes-in-windows-forms-controls.md)
- [Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
