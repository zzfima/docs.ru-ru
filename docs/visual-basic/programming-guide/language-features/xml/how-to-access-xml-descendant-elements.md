---
title: Практическое руководство. Доступ к элементам-потомкам XML
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347160"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="2a313-102">Практическое руководство. Доступ к производным XML элементам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a313-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="2a313-103">В этом примере показано, как использовать свойство оси потомков для доступа ко всем XML-элементам с указанным именем и содержащимся в XML-элементе.</span><span class="sxs-lookup"><span data-stu-id="2a313-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="2a313-104">В частности, используется свойство `Value` для получения значения первого элемента в коллекции, возвращаемого свойством дочерней оси `name`.</span><span class="sxs-lookup"><span data-stu-id="2a313-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="2a313-105">Свойство "дочерняя ось `name`" получает все элементы с именами `name`, которые содержатся в объекте `contacts`.</span><span class="sxs-lookup"><span data-stu-id="2a313-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="2a313-106">В этом примере также используется свойство дочерней оси `phone` для доступа ко всем потомкам с именем `phone`, содержащимся в объекте `contacts`.</span><span class="sxs-lookup"><span data-stu-id="2a313-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a313-107">Пример</span><span class="sxs-lookup"><span data-stu-id="2a313-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="2a313-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2a313-108">Compile the code</span></span>  
 <span data-ttu-id="2a313-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2a313-109">This example requires:</span></span>  
  
- <span data-ttu-id="2a313-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="2a313-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a313-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2a313-111">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2a313-112">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="2a313-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="2a313-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="2a313-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="2a313-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2a313-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [<span data-ttu-id="2a313-115">XML</span><span class="sxs-lookup"><span data-stu-id="2a313-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
