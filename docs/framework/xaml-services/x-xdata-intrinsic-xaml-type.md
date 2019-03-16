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
ms.openlocfilehash: 68468c3c10fd884cf5fb92160e3cde41dbf7d529
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "58030264"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Встроенный тип XAML x:XData
Обеспечивает размещение острова данных XML в пределах рабочей XAML. XML-элементы в `x:XData` не следует обрабатывать процессорами XAML, как если бы они были частью пространства имен XAML по умолчанию действующего или любое другое пространство имен XAML. `x:XData` может содержать произвольное XML правильного формата.  
  
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
|`elementDataRoot`|Единственный корневой элемент вложенной области данных. Для большинства итоговой потребителей XML, который имеет один корневой считается недопустимым. В частности, один корень является обязательным, если `x:XData` предназначен как источник данных XML для WPF и многих других технологий, использующих источники XML для привязки данных.|  
|`[elementData]`|Необязательный параметр. XML, который представляет XML-данные. Как элемент данных может содержаться любое количество элементов и вложенных элементов, которые могут содержаться в других элементах; Тем не менее применить общие правила из XML.|  
  
## <a name="remarks"></a>Примечания  
 XML-элементы в `x:XData` объект можно повторно объявить все возможные пространства имен и префиксы содержащего XMLDOM в данных.  
  
 Программный доступ к XML-данных и `x:XData` возможен встроенный тип XAML в службах XAML .NET Framework через <xref:System.Windows.Markup.XData> класса.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 `x:XData` Объекта в основном используется в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider>, или вариант, в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> свойство (в XAML, это обычно выражается в синтаксис элемента свойства).  
  
 Как правило, данные должны переопределять базовое пространство имен XML в пределах острова данных, чтобы быть новое пространство имен XML по умолчанию (присваивается пустая строка). Это самый простой для простых данных о-ва поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражениям, используемым для ссылки и привязки к данным можно избежать префиксов. Более сложные острова данных может определить несколько префиксов для данных и использовать специальный префикс для пространства имен XML в корне. В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылки выражение должно включать соответствующий префикс сопоставления пространства имен. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../wpf/data/data-binding-overview.md).  
  
 С технической точки зрения `x:XData` можно использовать в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>. Тем не менее <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> представляет собой реализацию только заметной.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Data.XmlDataProvider>
- [Общие сведения о привязке данных](../wpf/data/data-binding-overview.md)
- [Привязка расширения разметки](../wpf/advanced/binding-markup-extension.md)
