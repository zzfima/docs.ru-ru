---
title: "Поддержка функции msxsl:node-set() | Microsoft Docs"
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
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Поддержка функции msxsl:node-set()
Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов.  Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.  
  
> [!NOTE]
>  Класс <xref:System.Xml.Xsl.XslTransform> в версии [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] устарел.  Можно выполнять XSLT\-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.  Дополнительные сведения см. в разделах [Использование класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [Миграция с класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов.  Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.  
  
## Пример  
 В следующем примере `$var` \- переменная, представляющая собой дерево узлов в таблице стилей.  Инструкция for\-each в сочетании с функцией `node-set` позволяет пользователю проходить по этому дереву узлов как по набору узлов.  
  
## nodeset.xsl  
  
```  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">   
                <author><xsl:value-of select="@author"/)</author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## Вывод  
 Выходные данные преобразования:  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## См. также  
 [Реализация классом XslTransform XSLT\-процессора](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)