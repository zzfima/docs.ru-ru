---
title: Практическое руководство. Элементам-потомкам XML доступа (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: bfbf849bd296f639f03580346e4a9c52ce000abd
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832220"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="88960-102">Практическое руководство. Элементам-потомкам XML доступа (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88960-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="88960-103">В этом примере показано, как использовать свойства дочерней оси для доступа ко всем элементам XML с указанным именем, содержащиеся в XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="88960-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="88960-104">В частности, он использует `Value` свойство, чтобы получить значение первого элемента в коллекции, `name` возвращает свойство дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="88960-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="88960-105">`name` Descendant axis-свойство возвращает все элементы с именем `name` , содержащихся в `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="88960-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="88960-106">В этом примере также используется `phone` descendant axis-свойство для доступа к всех наследников с именем `phone` , содержащихся в `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="88960-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88960-107">Пример</span><span class="sxs-lookup"><span data-stu-id="88960-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88960-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="88960-108">Compiling the Code</span></span>  
 <span data-ttu-id="88960-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="88960-109">This example requires:</span></span>  
  
-   <span data-ttu-id="88960-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="88960-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88960-111">См. также</span><span class="sxs-lookup"><span data-stu-id="88960-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="88960-112">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="88960-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="88960-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="88960-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="88960-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88960-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="88960-115">XML</span><span class="sxs-lookup"><span data-stu-id="88960-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
