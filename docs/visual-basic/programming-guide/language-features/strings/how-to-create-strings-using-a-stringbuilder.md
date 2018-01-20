---
title: "Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9def5da754d9075a8b498ac80e624caae5c97b96
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="6acec-102">Практическое руководство. Создание строки с помощью StringBuilder в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6acec-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="6acec-103">В этом примере создается длинная строка из множества маленьких строк с помощью <xref:System.Text.StringBuilder> класса.</span><span class="sxs-lookup"><span data-stu-id="6acec-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="6acec-104"><xref:System.Text.StringBuilder> Класс является более эффективным, чем `&=` оператора для сложения нескольких строк.</span><span class="sxs-lookup"><span data-stu-id="6acec-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6acec-105">Пример</span><span class="sxs-lookup"><span data-stu-id="6acec-105">Example</span></span>  
 <span data-ttu-id="6acec-106">В следующем примере создается экземпляр <xref:System.Text.StringBuilder> прибавляется 1 000 строк к этому экземпляру класса и возвращает его строковое представление.</span><span class="sxs-lookup"><span data-stu-id="6acec-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6acec-107">См. также</span><span class="sxs-lookup"><span data-stu-id="6acec-107">See Also</span></span>  
 <span data-ttu-id="6acec-108">[Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)</span><span class="sxs-lookup"><span data-stu-id="6acec-108">[Using the StringBuilder Class](../../../../standard/base-types/stringbuilder.md)</span></span>  
 [<span data-ttu-id="6acec-109">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="6acec-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [<span data-ttu-id="6acec-110">Строки</span><span class="sxs-lookup"><span data-stu-id="6acec-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="6acec-111">Создание строк</span><span class="sxs-lookup"><span data-stu-id="6acec-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)  
 [<span data-ttu-id="6acec-112">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="6acec-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)  
 [<span data-ttu-id="6acec-113">Пример строк</span><span class="sxs-lookup"><span data-stu-id="6acec-113">Strings Sample</span></span>](http://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02)
