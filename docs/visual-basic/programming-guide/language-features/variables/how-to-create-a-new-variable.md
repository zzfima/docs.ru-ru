---
title: "Практическое руководство: Создание новой переменной (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 3b5aa4e5e0b84f41ac3df73bc70d8402d10b21a2
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="f404e-102">Практическое руководство. Создание новой переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f404e-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="f404e-103">Создайте переменную с [оператора Dim](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f404e-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="f404e-104">Создание новой переменной</span><span class="sxs-lookup"><span data-stu-id="f404e-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="f404e-105">Объявите переменную в `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f404e-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="f404e-106">Включают спецификации для переменной характеристики, такие как [частного](../../../../visual-basic/language-reference/modifiers/private.md), [статических](../../../../visual-basic/language-reference/modifiers/static.md), [тени](../../../../visual-basic/language-reference/modifiers/shadows.md), или [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="f404e-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="f404e-107">Дополнительные сведения см. в разделе [характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="f404e-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="f404e-108">Не требуется `Dim` ключевое слово, при использовании других ключевых слов в объявлении.</span><span class="sxs-lookup"><span data-stu-id="f404e-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="f404e-109">За спецификацией должно следовать имя переменной, которой должны следовать [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] правила и соглашения.</span><span class="sxs-lookup"><span data-stu-id="f404e-109">Follow the specifications with the variable's name, which must follow [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rules and conventions.</span></span> <span data-ttu-id="f404e-110">Дополнительные сведения см. в разделе [имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="f404e-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="f404e-111">После имени [как](../../../../visual-basic/language-reference/statements/as-clause.md) предложение, чтобы указать тип данных переменной.</span><span class="sxs-lookup"><span data-stu-id="f404e-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="f404e-112">Если тип данных не указан, используется значение по умолчанию: `Object`.</span><span class="sxs-lookup"><span data-stu-id="f404e-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="f404e-113">Выполните `As` предложение со знака равенства (`=`) и за ним начальное значение переменной.</span><span class="sxs-lookup"><span data-stu-id="f404e-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f404e-114">Присваивает указанное значение переменной при каждом запуске `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f404e-114"> assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="f404e-115">Если не указать начальное значение, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] назначает начальное значение по умолчанию для типа данных переменной при первом выполнении кода, содержащего `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="f404e-115">If you do not specify an initial value, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="f404e-116">Если переменная является ссылочным типом, можно создать экземпляр класса, включая [оператор New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово в `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="f404e-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="f404e-117">Если вы не используете `New`, начальное значение переменной равно [ничего не](../../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="f404e-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f404e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f404e-118">See Also</span></span>  
 <span data-ttu-id="f404e-119">[Переменные](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-119">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="f404e-120"> [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-120"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="f404e-121"> [Имена объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-121"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="f404e-122"> [Характеристики объявленных элементов](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-122"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="f404e-123"> [Типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-123"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="f404e-124"> [Инструкции](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-124"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="f404e-125"> [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="f404e-125"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="f404e-126"> [Оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="f404e-126"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>

