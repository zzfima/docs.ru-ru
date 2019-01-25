---
title: Как выполнить Создание строк с помощью StringBuilder в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 84f0f41cf8ee23466d47dae3b1068c3bc5334072
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528450"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="34246-102">Как выполнить Создание строк с помощью StringBuilder в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="34246-102">How to: Create Strings Using a StringBuilder in Visual Basic</span></span>
<span data-ttu-id="34246-103">В этом примере создается длинная строка из множества маленьких строк с помощью <xref:System.Text.StringBuilder> класса.</span><span class="sxs-lookup"><span data-stu-id="34246-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="34246-104"><xref:System.Text.StringBuilder> Класс является более эффективным, чем `&=` оператор для объединения большого количества строк.</span><span class="sxs-lookup"><span data-stu-id="34246-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34246-105">Пример</span><span class="sxs-lookup"><span data-stu-id="34246-105">Example</span></span>  
 <span data-ttu-id="34246-106">В следующем примере создается экземпляр <xref:System.Text.StringBuilder> класс, прибавляется 1 000 строк к этому экземпляру, а затем возвращает его строковое представление.</span><span class="sxs-lookup"><span data-stu-id="34246-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation.</span></span>  
  
 [!code-vb[VbVbalrStrings#70](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-strings-using-a-stringbuilder_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="34246-107">См. также</span><span class="sxs-lookup"><span data-stu-id="34246-107">See also</span></span>
- <span data-ttu-id="34246-108">[Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)</span><span class="sxs-lookup"><span data-stu-id="34246-108">[Using the StringBuilder Class](../../../../standard/base-types/stringbuilder.md)</span></span>
- [<span data-ttu-id="34246-109">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="34246-109">&= Operator</span></span>](../../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="34246-110">Строки</span><span class="sxs-lookup"><span data-stu-id="34246-110">Strings</span></span>](../../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="34246-111">Создание строк</span><span class="sxs-lookup"><span data-stu-id="34246-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="34246-112">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="34246-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
- <span data-ttu-id="34246-113">[Пример строк](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="34246-113">[Strings Sample](https://msdn.microsoft.com/library/be9e82a3-dc95-4aaa-9396-61b66e467e02(v=vs.100))</span></span>
