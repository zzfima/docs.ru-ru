---
title: Пошаговое руководство. перебор перечислений
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354026"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="7deea-102">Практическое руководство. Перебор элементов перечисления в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7deea-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="7deea-103">Перечисления — это удобный способ работать с наборами связанных констант и связывать постоянные значения с именами.</span><span class="sxs-lookup"><span data-stu-id="7deea-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="7deea-104">Чтобы выполнить итерацию по перечислению, можно переместить его в массив с помощью метода <xref:System.Enum.GetValues%2A>.</span><span class="sxs-lookup"><span data-stu-id="7deea-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="7deea-105">Можно также выполнить итерацию перечисления с помощью оператора `For...Each`, используя метод <xref:System.Enum.GetNames%2A> или <xref:System.Enum.GetValues%2A> для извлечения строкового или числового значения.</span><span class="sxs-lookup"><span data-stu-id="7deea-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="7deea-106">Перебор перечислений</span><span class="sxs-lookup"><span data-stu-id="7deea-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="7deea-107">Объявите массив и преобразуйте перечисление в него с помощью метода <xref:System.Enum.GetValues%2A>, прежде чем передавать массив, как и любую другую переменную.</span><span class="sxs-lookup"><span data-stu-id="7deea-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="7deea-108">В следующем примере каждый элемент перечисления выводится <xref:Microsoft.VisualBasic.FirstDayOfWeek> в процессе итерации по перечислению.</span><span class="sxs-lookup"><span data-stu-id="7deea-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="7deea-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7deea-109">See also</span></span>

- [<span data-ttu-id="7deea-110">Общие сведения о перечислениях</span><span class="sxs-lookup"><span data-stu-id="7deea-110">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="7deea-111">Инструкции. Объявление перечисления</span><span class="sxs-lookup"><span data-stu-id="7deea-111">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="7deea-112">Когда следует использовать перечисление</span><span class="sxs-lookup"><span data-stu-id="7deea-112">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [<span data-ttu-id="7deea-113">Практическое руководство. Определение строки, связанной со значением из перечисления</span><span class="sxs-lookup"><span data-stu-id="7deea-113">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="7deea-114">Практическое руководство. Ссылка на элемент перечисления</span><span class="sxs-lookup"><span data-stu-id="7deea-114">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="7deea-115">Перечисления и уточнение имен</span><span class="sxs-lookup"><span data-stu-id="7deea-115">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="7deea-116">Массивы</span><span class="sxs-lookup"><span data-stu-id="7deea-116">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
