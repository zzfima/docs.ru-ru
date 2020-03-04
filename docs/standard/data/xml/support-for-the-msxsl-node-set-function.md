---
title: Поддержка функции msxsl:node-set()
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
ms.openlocfilehash: 5022b298cb20796edbc54e951d8b06043697d832
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155598"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="8d2c4-102">Поддержка функции msxsl:node-set()</span><span class="sxs-lookup"><span data-stu-id="8d2c4-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="8d2c4-103">Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="8d2c4-104">Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d2c4-105">Класс <xref:System.Xml.Xsl.XslTransform> явлется устаревшим в версии .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="8d2c4-106">Можно выполнять XSLT-преобразование, используя класс <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="8d2c4-107">См. дополнительные сведения об [использовании класса XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) и [миграции из класса XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="8d2c4-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="8d2c4-108">Функция `msxsl:node-set` позволяет преобразовать фрагмент дерева результатов в набор узлов.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="8d2c4-109">Получаемый в результате набор узлов всегда содержит один узел, который является корневым узлом дерева.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d2c4-110">Пример</span><span class="sxs-lookup"><span data-stu-id="8d2c4-110">Example</span></span>  
 <span data-ttu-id="8d2c4-111">В следующем примере `$var` - переменная, представляющая собой дерево узлов в таблице стилей.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="8d2c4-112">Инструкция for-each в сочетании с функцией `node-set` позволяет пользователю проходить по этому дереву узлов как по набору узлов.</span><span class="sxs-lookup"><span data-stu-id="8d2c4-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="8d2c4-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="8d2c4-113">nodeset.xsl</span></span>  
  
```xml  
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
                <author><xsl:value-of select="@author"/></author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="8d2c4-114">Выходные данные</span><span class="sxs-lookup"><span data-stu-id="8d2c4-114">Output</span></span>  
 <span data-ttu-id="8d2c4-115">Выходные данные преобразования:</span><span class="sxs-lookup"><span data-stu-id="8d2c4-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8d2c4-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d2c4-116">See also</span></span>

- [<span data-ttu-id="8d2c4-117">Реализация классом XslTransform XSLT-процессора</span><span class="sxs-lookup"><span data-stu-id="8d2c4-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
