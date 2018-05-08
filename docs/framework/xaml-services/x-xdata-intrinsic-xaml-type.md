---
title: Встроенный тип XAML x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 3a16379fd6104342529723bf6d0bc9fb4762cf92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="xxdata-intrinsic-xaml-type"></a>Встроенный тип XAML x:XData
Обеспечивает размещение острова данных XML в пределах рабочей среды XAML. XML-элементы в `x:XData` не следует обрабатывать обработчиками XAML, как если бы они были частью пространства имен XAML по умолчанию действующего или любое другое пространство имен XAML. `x:XData` может содержать произвольный корректный XML.  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Единственный корневой элемент вложенной области данных. Для большинства окончательной потребителей XML, который имеет один корневой считается недействительным. В частности, один корень является обязательным, если `x:XData` предназначен как источник данных XML для WPF и многих других технологий, использующих источники XML для привязки данных.|  
|`[elementData]`|Необязательный. XML-ФАЙЛ, который представляет XML-данные. Как элемент данных может содержаться любое количество элементов и вложенные элементы, которые могут содержаться в других элементах; Однако применить общие правила XML.|  
  
## <a name="remarks"></a>Примечания  
 XML-элементы в `x:XData` объекта могут повторно объявлять все возможные пространства имен и префиксы внешней XML DOM в данных.  
  
 Программный доступ к XML-данных и `x:XData` возможен встроенный тип XAML в службах XAML .NET Framework по <xref:System.Windows.Markup.XData> класса.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 `x:XData` Объекта в основном используется как дочерний объект <xref:System.Windows.Data.XmlDataProvider>, то же, как дочерний объект <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> свойство (XAML, это обычно выражается в синтаксис элемента свойства).  
  
 Как правило, данные должны переопределять базовое пространство имен XML в пределах острова данных для нового пространства имен XML по умолчанию (задается пустая строка). Это проще всего для простых данных о-ва поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражениям, используемым для ссылки и привязки к данным можно избежать префиксов. Более сложные острова данных может определить несколько префиксов для данных и использовать специальный префикс для пространства имен XML в корне. В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылках в выражениях следует включить соответствующий префикс сопоставлены пространств имен. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 С технической точки зрения `x:XData` можно использовать в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>. Тем не менее <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> является только Показательным реализацией.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Data.XmlDataProvider>  
 [Общие сведения о привязке данных](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Привязка расширения разметки](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
