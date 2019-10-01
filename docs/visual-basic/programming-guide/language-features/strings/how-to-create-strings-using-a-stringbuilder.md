---
title: Инструкции. Создание строк с помощью StringBuilder в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- StringBuilder class
- strings [Visual Basic], using StringBuilder
ms.assetid: 9c042880-aa16-432e-9ccb-cd00abda9ae3
ms.openlocfilehash: 19e036abc9d25ec7fdfd6c33ebb420ec4f503cbc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700111"
---
# <a name="how-to-create-strings-using-a-stringbuilder-in-visual-basic"></a><span data-ttu-id="affc4-102">Инструкции. Создание строк с помощью StringBuilder в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="affc4-102">How to: create strings using a StringBuilder in Visual Basic</span></span>

<span data-ttu-id="affc4-103">В этом примере создается длинная строка из множества меньших строк с использованием класса <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="affc4-103">This example constructs a long string from many smaller strings using the <xref:System.Text.StringBuilder> class.</span></span> <span data-ttu-id="affc4-104">Класс <xref:System.Text.StringBuilder> более эффективен, чем оператор `&=` для сцепления многих строк.</span><span class="sxs-lookup"><span data-stu-id="affc4-104">The <xref:System.Text.StringBuilder> class is more efficient than the `&=` operator for concatenating many strings.</span></span>

## <a name="example"></a><span data-ttu-id="affc4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="affc4-105">Example</span></span>

<span data-ttu-id="affc4-106">В следующем примере создается экземпляр класса <xref:System.Text.StringBuilder>, добавляются строки 1 000 в этот экземпляр, а затем возвращается строковое представление:</span><span class="sxs-lookup"><span data-stu-id="affc4-106">The following example creates an instance of the <xref:System.Text.StringBuilder> class, appends 1,000 strings to that instance, and then returns its string representation:</span></span>

 [!code-vb[VbVbalrStrings#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#70)]

## <a name="see-also"></a><span data-ttu-id="affc4-107">См. также</span><span class="sxs-lookup"><span data-stu-id="affc4-107">See also</span></span>

- <span data-ttu-id="affc4-108">[Using the StringBuilder class](../../../../standard/base-types/stringbuilder.md) (Использование класса StringBuilder)</span><span class="sxs-lookup"><span data-stu-id="affc4-108">[Using the StringBuilder Class](../../../../standard/base-types/stringbuilder.md)</span></span>
- [<span data-ttu-id="affc4-109">Оператор &=</span><span class="sxs-lookup"><span data-stu-id="affc4-109">&= Operator</span></span>](../../../language-reference/operators/and-assignment-operator.md)
- [<span data-ttu-id="affc4-110">Строки</span><span class="sxs-lookup"><span data-stu-id="affc4-110">Strings</span></span>](index.md)
- [<span data-ttu-id="affc4-111">Создание строк</span><span class="sxs-lookup"><span data-stu-id="affc4-111">Creating New Strings</span></span>](../../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="affc4-112">Операции со строками</span><span class="sxs-lookup"><span data-stu-id="affc4-112">Manipulating Strings</span></span>](../../../../standard/base-types/manipulating-strings.md)
