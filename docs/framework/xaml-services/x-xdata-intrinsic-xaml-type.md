---
title: "x:XData Intrinsic XAML Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:XData"
  - "XData"
  - "xXData"
helpviewer_keywords: 
  - "XAML [XAML Services], x:XData directive element"
  - "XData in XAML [XAML Services]"
  - "x:XData XAML directive element [XAML Services]"
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: 17
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 17
---
# x:XData Intrinsic XAML Type
Разрешает размещение островов данных XML в пределах производства XAML.  Элементы XML внутри данного элемента `x:XData` не должны рассматриваться средствами обработки XAML как часть действующего по умолчанию пространства имен XAML или любого другого пространства имен XAML.  `x:XData` может содержать произвольный корректный XML.  
  
## Использование элемента объекта XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## Значения XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Один корневой элемент вложенного острова данных.  Для большинства конечным потребителей XML, который имеет один корневой элемент, считается недопустимым.  В частности, требуется единственный корень, если предполагается, что `x:XData` будет источником данных XML для WPF или многих других технологий, которые используют источники XML для привязки данных.|  
|`[elementData]`|Необязательный.  XML, представляющий данные XML.  Любое число элементов может содержаться в качестве данных элемента, и вложенные элементы могут содержаться в других элементах. Однако применяются общие правила XML.|  
  
## Заметки  
 XML\-элементы в объекте `x:XData` могут повторно объявлять все возможные пространства имен и префиксы внешней XML DOM в пределах данных.  
  
 Программный доступ к XML\-данным и встроенному типу XAML `x:XData` осуществляется в службах XAML .NET Framework через класс <xref:System.Windows.Markup.XData>.  
  
## Примечания об использовании WPF  
 Объект `x:XData` главным образом используется как дочерний объект поставщика <xref:System.Windows.Data.XmlDataProvider> или как дочерний объект свойства <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName> \(в XAML обычно выражается в синтаксисе элемента свойства\).  
  
 Как правило, данные должны переопределять базовый XML\-код в острове данных таким образом, чтобы он стал новым XML\-кодом по умолчанию \(присваивается пустая строка\).  Это легче всего осуществить с островами простых данных, поскольку выражения <xref:System.Windows.Data.Binding.XPath%2A>, используемые для ссылки и привязки к данным, могут использоваться без префиксов.  В более сложных островах данных можно определить несколько префиксов для данных и использовать специальный префикс для пространства имен XML в корневом элементе.  В этом случае все ссылки выражения <xref:System.Windows.Data.Binding.XPath%2A> должны включать соответствующий префикс пространства имен.  Дополнительные сведения см. в разделе [Общие сведения о связывании данных](../../../ocs/framework/wpf/data/data-binding-overview.md).  
  
 С технической точки зрения `x:XData` можно использовать как содержимое любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>.  Однако, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName> является единственной значимой реализацией.  
  
## См. также  
 <xref:System.Windows.Data.XmlDataProvider>   
 [Общие сведения о связывании данных](../../../ocs/framework/wpf/data/data-binding-overview.md)   
 [Привязка расширения разметки](../../../ocs/framework/wpf/advanced/binding-markup-extension.md)