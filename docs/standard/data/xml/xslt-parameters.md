---
title: Параметры XSLT
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fe60aaa0-ae43-4b1c-9be1-426af66ba757
ms.openlocfilehash: cc412042e69a43bbecec9dbe68618e2d307ca793
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709703"
---
# <a name="xslt-parameters"></a>Параметры XSLT
Параметры XSLT добавляются в <xref:System.Xml.Xsl.XsltArgumentList> с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>. В это время с объектом параметра связываются полное имя и URI-код пространства имен.  
  
### <a name="to-use-an-xslt-parameter"></a>Использование параметра XSLT  
  
1. Создайте объект <xref:System.Xml.Xsl.XsltArgumentList> и добавьте параметр с помощью метода <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A>.  
  
2. Вызовите параметр из таблицы стилей.  
  
3. Передайте объект <xref:System.Xml.Xsl.XsltArgumentList> методу <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>.  
  
## <a name="parameter-types"></a>Типы параметров  
 Объект параметра должен соответствовать типу W3C. В следующей таблице показано соответствие типов W3C и классов (типов) Microsoft .NET. Также показано, является ли тип W3C типом XPath или типом XSLT.  
  
|Тип W3C|Эквивалентный класс (тип) .NET|Тип XPath или XSLT|  
|--------------|------------------------------------|------------------------|  
|`String`|<xref:System.String?displayProperty=nameWithType>|XPath|  
|`Boolean`|<xref:System.Boolean?displayProperty=nameWithType>|XPath|  
|`Number`|<xref:System.Double?displayProperty=nameWithType>|XPath|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|XSLT|  
|`Node*`|<xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>|XPath|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator><br /><br /> **XPathNavigator[]**|XPath|  
  
 *Это эквивалентно набору узлов, содержащему единственный узел.  
  
 Если объект параметра не принадлежит ни к одному из приведенных выше классов, он преобразуется по следующим правилам. Числовые типы среды CLR преобразуются в <xref:System.Double>. Тип <xref:System.DateTime> преобразуется в тип <xref:System.String>. Типы <xref:System.Xml.XPath.IXPathNavigable> преобразуются в типы <xref:System.Xml.XPath.XPathNavigator>. **XPathNavigator[]** преобразуется в <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Все другие типы вызывают ошибку.  
  
## <a name="example"></a>Пример  
 В следующем примере используется метод <xref:System.Xml.Xsl.XsltArgumentList.AddParam%2A> для создания параметра, хранящего вычисленную дату скидки. Дата скидки вычисляется как 20 дней после даты заказа.  
  
 [!code-csharp[XSLT_Param#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Param/CS/xsltparam.cs#1)]
 [!code-vb[XSLT_Param#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Param/VB/xsltparam.vb#1)]  
  
### <a name="input"></a>Input  
  
##### <a name="orderxml"></a>order.xml  
 [!code-xml[XSLT_Param#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/order.xml#2)]  
  
##### <a name="discountxsl"></a>discount.xsl  
 [!code-xml[XSLT_Param#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Param/XML/discount.xsl#3)]  
  
### <a name="output"></a>Вывод  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<order>  
  <total>36.9</total>  
     15% discount if paid by: 2/4/2004 12:00:00 AM  
</order>  
```  
  
## <a name="see-also"></a>См. также:

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
