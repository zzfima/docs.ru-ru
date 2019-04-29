---
title: расширение разметки x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938883"
---
# <a name="xreference-markup-extension"></a>расширение разметки x:Reference
Ссылается на экземпляр, который объявлен в другом месте в разметке XAML. Ссылка на элемент `x:Name`.  
  
## <a name="xaml-attribute-usage"></a>Использование атрибута XAML  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`instancexName`|`x:Name` Значение (или значение <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-определить свойства) экземпляра, на который указывает ссылка.|  
  
## <a name="remarks"></a>Примечания  
 `x:Reference` обеспечивает поддержку уровня языка XAML понятие ссылки элемент, в противном случае было реализовано в конкретных платформах, таких как WPF.  
  
## <a name="xreference-and-wpf"></a>x: Reference и WPF  
 В WPF и XAML 2006, ссылки на элементы будут удовлетворены функцией уровня платформы <xref:System.Windows.Data.Binding.ElementName%2A> привязки. Для большинства приложений WPF и сценариев <xref:System.Windows.Data.Binding.ElementName%2A> привязка должна использоваться. Исключения из этого общего правила могут быть случаи, где контекст данных или другие соображения, которые делают нецелесообразным привязки данных и не участвует компиляции разметки.  
  
 `x:Reference` Это конструкция, определенные в XAML 2009 г. В WPF можно использовать возможности XAML 2009, но только для кода XAML, не скомпилированного с разметкой WPF. Скомпилированный XAML с разметкой и форма BAML кода XAML пока не поддерживают ключевые слова языка и компоненты XAML 2009.
