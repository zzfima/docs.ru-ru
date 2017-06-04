---
title: "Наборы узлов в преобразованиях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# Наборы узлов в преобразованиях
Наборы узлов \- это один из четырех базовых типов данных, возвращаемых из выражений на языке XPath. Набор узлов, представляющий собой неупорядоченную коллекцию узлов без повторов, созданную в порядке документа, может быть назначен переменной в таблице стилей.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел. Можно выполнять XSLT\-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>. Дополнительные сведения см. в разделах [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Наборы узлов \- это один из четырех базовых типов данных, возвращаемых из выражений на языке XPath. Набор узлов, представляющий собой неупорядоченную коллекцию узлов без повторов, созданную в порядке документа, может быть назначен переменной в таблице стилей. Этот набор узлов, являющийся результатом выражения XPath, которое используется в атрибуте `select` при преобразовании, имеет такое же поведение, как и набор узлов из модели DOM. Перемещаться по набору узлов можно с помощью набора методов, показанного в разделе [Навигация в наборе узлов с помощью XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), в отличие от фрагментов результирующего дерева, которые для перехода используют объект <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Следующий образец кода демонстрирует, как проходить по набору узлов, если результатом вычисления элемента `variable` или `parameter` в таблице стилей является набор узлов.  
  
## Таблица стилей  
  
```  
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
  
## Ввод  
  
```  
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
  
## Вывод  
  
```  
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
  
## См. также  
 <xref:System.Xml.XPath.XPathNodeIterator>   
 [XSLT\-преобразования с помощью класса XslTransform](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)   
 [Реализация классом XslTransform XSLT\-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)