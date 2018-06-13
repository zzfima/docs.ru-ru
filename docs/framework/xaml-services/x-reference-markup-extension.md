---
title: расширение разметки x:Reference
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562249"
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
|`instancexName`|`x:Name` Значение (или значение <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-определенных свойств) экземпляра, на который указывает ссылка.|  
  
## <a name="remarks"></a>Примечания  
 `x:Reference` обеспечивает поддержку уровня языка XAML понятие ссылки элемента, в противном случае было реализовано в конкретных платформах, таких как WPF.  
  
## <a name="xreference-and-wpf"></a>x: Reference и WPF  
 В WPF и XAML 2006, ссылки на элемент адресуются с помощью функции уровня инфраструктуры <xref:System.Windows.Data.Binding.ElementName%2A> привязки. Для большинства приложений WPF и сценарии <xref:System.Windows.Data.Binding.ElementName%2A> привязки должен использоваться. Исключения из этого общего правила могут быть случаи, где существует контекст данных или другие соображения, которые делают привязку данных непрактичной и где компиляции разметки не участвует.  
  
 `x:Reference` Это конструкция, определенные в XAML 2009. В WPF можно использовать возможности XAML 2009, но только для кода XAML, не скомпилированного с разметкой WPF. Скомпилированный XAML с разметкой и форма BAML кода XAML пока не поддерживают ключевые слова языка и компоненты XAML 2009.
