---
title: Наборы узлов в преобразованиях
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
ms.openlocfilehash: 2828b95f6a4050dd05b38e7ab6ef740ee4eb16b4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710561"
---
# <a name="node-sets-in-transformations"></a>Наборы узлов в преобразованиях
Наборы узлов - это один из четырех базовых типов данных, возвращаемых из выражений на языке XPath. Набор узлов, представляющий собой неупорядоченную коллекцию узлов без повторов, созданную в порядке документа, может быть назначен переменной в таблице стилей.  
  
> [!NOTE]
> Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0. Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Наборы узлов - это один из четырех базовых типов данных, возвращаемых из выражений на языке XPath. Набор узлов, представляющий собой неупорядоченную коллекцию узлов без повторов, созданную в порядке документа, может быть назначен переменной в таблице стилей. Этот набор узлов, являющийся результатом выражения XPath, которое используется в атрибуте `select` при преобразовании, имеет такое же поведение, как и набор узлов из модели DOM. [Перемещаться по набору узлов можно с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), в отличие от фрагментов результирующего дерева, которые для перехода используют <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Следующий образец кода демонстрирует, как проходить по набору узлов, если результатом вычисления элемента `variable` или `parameter` в таблице стилей является набор узлов.  
  
## <a name="style-sheet"></a>Таблица стилей  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a>Input  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a>Вывод  
  
```output  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Xml.XPath.XPathNodeIterator>
- [XSLT-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [Реализация классом XslTransform XSLT-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
