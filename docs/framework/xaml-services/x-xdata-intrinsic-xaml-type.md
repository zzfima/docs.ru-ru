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
ms.openlocfilehash: c5f729837b9bb52ca7d232ca66b58e283a2bcefc
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053696"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Встроенный тип XAML x:XData
Включает размещение островов XML-данных в рабочей среде XAML. XML-элементы `x:XData` внутри не должны обрабатываться обработчиками XAML так, как если бы они были частью действующего пространства имен XAML по умолчанию или любого другого пространства имен XAML. `x:XData`может содержать произвольный XML-файл правильного формата.  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Единственный корневой элемент вложенного острова данных. Для большинства конечных потребителей XML, не имеющий одного корня, считается недопустимым. В частности, один корневой элемент необходим, если `x:XData` класс предназначен для использования в качестве источника данных XML для WPF или многих других технологий, использующих источники XML для привязки данных.|  
|`[elementData]`|Необязательный параметр. XML, представляющий XML-данные. В качестве данных элемента может содержаться любое количество элементов, а вложенные элементы могут содержаться в других элементах. Однако применяются общие правила XML.|  
  
## <a name="remarks"></a>Примечания  
 XML-элементы внутри `x:XData` объекта могут повторно объявить все возможные пространства имен и префиксы, содержащиеся в данных XMLDOM.  
  
 Программный доступ к XML-данным `x:XData` и встроенный тип XAML можно использовать в .NET Framework службах XAML <xref:System.Windows.Markup.XData> через класс.  
  
## <a name="wpf-usage-notes"></a>Примечания об использовании WPF  
 Объект в основном используется в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider>(или) в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> свойства (в XAML это обычно выражается в синтаксисе элемента свойства). `x:XData`  
  
 Данные обычно должны переопределять базовое пространство имен XML в области данных, чтобы стать новым пространством имен XML по умолчанию (для которого задана пустая строка). Это проще всего для простых островов данных, поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражения, используемые для ссылки на данные и привязки к ним, могут не включать префиксы. Более сложные острова данных могут определять несколько префиксов для данных и использовать конкретный префикс для пространства имен XML в корне. В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылки на выражения должны включать соответствующий префикс, сопоставленный с пространством имен. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../wpf/data/data-binding-overview.md).  
  
 Технически может использоваться в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>. `x:XData` <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Однако является единственной выразительной реализацией.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.XmlDataProvider>
- [Общие сведения о привязке данных](../wpf/data/data-binding-overview.md)
- [Привязка расширения разметки](../wpf/advanced/binding-markup-extension.md)
