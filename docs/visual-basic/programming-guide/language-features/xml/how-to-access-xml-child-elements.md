---
title: Практическое руководство. Доступа к дочерним XML-элементам (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: 3c00166e471b7c6d69bd7f6fc3bda87b651d7d46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598666"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a><span data-ttu-id="73606-102">Практическое руководство. Доступа к дочерним XML-элементам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="73606-102">How to: Access XML Child Elements (Visual Basic)</span></span>
<span data-ttu-id="73606-103">В этом примере показано, как использовать дочернего свойства оси для доступа к все дочерние элементы XML, которые имеют указанное имя элемента XML.</span><span class="sxs-lookup"><span data-stu-id="73606-103">This example shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span> <span data-ttu-id="73606-104">В частности, он использует <xref:System.Xml.Linq.XElement.Value%2A> свойство, чтобы получить значение первого элемента в коллекции, `name` возвращает свойство дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="73606-104">In particular, it uses the <xref:System.Xml.Linq.XElement.Value%2A> property to get the value of the first element in the collection that the `name` child axis property returns.</span></span> <span data-ttu-id="73606-105">`name` Child axis-свойство получает все дочерние элементы с именем `phone` в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="73606-105">The `name` child axis property gets all child elements named `phone` in the `contact` object.</span></span> <span data-ttu-id="73606-106">В этом примере также используется `phone` свойство дочерней оси для доступа к все дочерние элементы с именем `phone` , содержащихся в `contact` объекта.</span><span class="sxs-lookup"><span data-stu-id="73606-106">This example also uses the `phone` child axis property to access all child elements named `phone` that are contained in the `contact` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73606-107">Пример</span><span class="sxs-lookup"><span data-stu-id="73606-107">Example</span></span>  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73606-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="73606-108">Compiling the Code</span></span>  
 <span data-ttu-id="73606-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="73606-109">This example requires:</span></span>  
  
- <span data-ttu-id="73606-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="73606-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73606-111">См. также</span><span class="sxs-lookup"><span data-stu-id="73606-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="73606-112">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="73606-112">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="73606-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="73606-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="73606-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="73606-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="73606-115">XML</span><span class="sxs-lookup"><span data-stu-id="73606-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
