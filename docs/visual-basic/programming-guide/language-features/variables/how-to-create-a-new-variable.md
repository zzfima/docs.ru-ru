---
title: Практическое руководство. Создание новой переменной (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: ee1e93b4e9819992f17738eb024004a4d66210d1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332590"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="72d9f-102">Практическое руководство. Создание новой переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72d9f-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="72d9f-103">Создайте переменную с [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="72d9f-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="72d9f-104">Создание новой переменной</span><span class="sxs-lookup"><span data-stu-id="72d9f-104">To create a new variable</span></span>  
  
1. <span data-ttu-id="72d9f-105">Объявить эту переменную в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="72d9f-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2. <span data-ttu-id="72d9f-106">Включают спецификации для переменной характеристики, такие как [частного](../../../../visual-basic/language-reference/modifiers/private.md), [статический](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="72d9f-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="72d9f-107">Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="72d9f-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="72d9f-108">Нет необходимости `Dim` ключевое слово, если вы используете другие ключевые слова в объявлении.</span><span class="sxs-lookup"><span data-stu-id="72d9f-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3. <span data-ttu-id="72d9f-109">За спецификацией имя переменной, должно соответствовать Visual Basic правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="72d9f-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="72d9f-110">Дополнительные сведения см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="72d9f-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4. <span data-ttu-id="72d9f-111">После имени [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение, чтобы указать тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="72d9f-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="72d9f-112">Если вы не укажете тип данных, используется значение по умолчанию: `Object`.</span><span class="sxs-lookup"><span data-stu-id="72d9f-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5. <span data-ttu-id="72d9f-113">Выполните `As` предложение со знака равенства (`=`) и следовать знак равенства с начальным значением переменной.</span><span class="sxs-lookup"><span data-stu-id="72d9f-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     <span data-ttu-id="72d9f-114">Visual Basic назначает указанное значение переменной, каждый раз при его запуске `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="72d9f-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="72d9f-115">Если начальное значение не задано, Visual Basic назначает начальное значение по умолчанию для типа данных переменной, при первом выполнении кода, содержащего `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="72d9f-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="72d9f-116">Если переменная является ссылочным типом, можно создать экземпляр своего класса, включая [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово в `As` предложение.</span><span class="sxs-lookup"><span data-stu-id="72d9f-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="72d9f-117">Если вы не используете `New`, начальное значение переменной равно [ничего не](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="72d9f-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="72d9f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="72d9f-118">See also</span></span>

- [<span data-ttu-id="72d9f-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="72d9f-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="72d9f-120">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="72d9f-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="72d9f-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="72d9f-121">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [<span data-ttu-id="72d9f-122">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="72d9f-122">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="72d9f-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="72d9f-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="72d9f-124">Операторы</span><span class="sxs-lookup"><span data-stu-id="72d9f-124">Statements</span></span>](../../../../visual-basic/language-reference/statements/index.md)
- [<span data-ttu-id="72d9f-125">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="72d9f-125">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="72d9f-126">Option Infer - оператор</span><span class="sxs-lookup"><span data-stu-id="72d9f-126">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
