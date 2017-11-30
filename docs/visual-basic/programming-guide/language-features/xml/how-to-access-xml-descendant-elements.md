---
title: "Практическое руководство. Доступ к производным XML элементам (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7b3b6c8ac96bd18a379804b83f3ab3e48a5b0c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="8bc9e-102">Практическое руководство. Доступ к производным XML элементам (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8bc9e-102">How to: Access XML Descendant Elements (Visual Basic)</span></span>
<span data-ttu-id="8bc9e-103">В этом примере показано, как использовать свойство дочерней оси для доступа ко всем элементам XML, с указанным именем, содержащиеся в XML-элемента.</span><span class="sxs-lookup"><span data-stu-id="8bc9e-103">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="8bc9e-104">В частности, он использует `Value` свойство, чтобы получить значение первого элемента в коллекции, `name` возвращает свойство дочерней оси.</span><span class="sxs-lookup"><span data-stu-id="8bc9e-104">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="8bc9e-105">`name` Свойство дочерней оси возвращает все элементы с именем `name` , содержащихся в `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="8bc9e-105">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="8bc9e-106">В этом примере также используется `phone` свойство дочерней оси для доступа ко всем потомкам с именем `phone` , содержащихся в `contacts` объекта.</span><span class="sxs-lookup"><span data-stu-id="8bc9e-106">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bc9e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8bc9e-107">Example</span></span>  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bc9e-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8bc9e-108">Compiling the Code</span></span>  
 <span data-ttu-id="8bc9e-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="8bc9e-109">This example requires:</span></span>  
  
-   <span data-ttu-id="8bc9e-110">ссылка на пространство имен <xref:System.Xml.Linq>.</span><span class="sxs-lookup"><span data-stu-id="8bc9e-110">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc9e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8bc9e-111">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="8bc9e-112">Свойство дочерней оси XML</span><span class="sxs-lookup"><span data-stu-id="8bc9e-112">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [<span data-ttu-id="8bc9e-113">Свойство значения XML</span><span class="sxs-lookup"><span data-stu-id="8bc9e-113">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [<span data-ttu-id="8bc9e-114">Доступ к XML в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8bc9e-114">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [<span data-ttu-id="8bc9e-115">XML</span><span class="sxs-lookup"><span data-stu-id="8bc9e-115">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
