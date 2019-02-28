---
title: Оператор TypeOf (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: 27fdef4012d4724d45b4e990ce449bdfe09feaa6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965063"
---
# <a name="typeof-operator-visual-basic"></a><span data-ttu-id="78d21-102">Оператор TypeOf (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78d21-102">TypeOf Operator (Visual Basic)</span></span>
<span data-ttu-id="78d21-103">Сравнивает переменную ссылки на объект с типом данных.</span><span class="sxs-lookup"><span data-stu-id="78d21-103">Compares an object reference variable to a data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78d21-104">Syntax</span></span>  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a><span data-ttu-id="78d21-105">Части</span><span class="sxs-lookup"><span data-stu-id="78d21-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="78d21-106">Возвращено.</span><span class="sxs-lookup"><span data-stu-id="78d21-106">Returned.</span></span> <span data-ttu-id="78d21-107">Значение `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="78d21-107">A `Boolean` value.</span></span>  
  
 `objectexpression`  
 <span data-ttu-id="78d21-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="78d21-108">Required.</span></span> <span data-ttu-id="78d21-109">Любое выражение, результатом которого является тип ссылки.</span><span class="sxs-lookup"><span data-stu-id="78d21-109">Any expression that evaluates to a reference type.</span></span>  
  
 `typename`  
 <span data-ttu-id="78d21-110">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="78d21-110">Required.</span></span> <span data-ttu-id="78d21-111">Любое имя типа данных.</span><span class="sxs-lookup"><span data-stu-id="78d21-111">Any data type name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78d21-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="78d21-112">Remarks</span></span>  
 <span data-ttu-id="78d21-113">Оператор `TypeOf` определяет, совместим ли тип времени выполнения `objectexpression` с `typename`.</span><span class="sxs-lookup"><span data-stu-id="78d21-113">The `TypeOf` operator determines whether the run-time type of `objectexpression` is compatible with `typename`.</span></span> <span data-ttu-id="78d21-114">Совместимость зависит от категории типа `typename`.</span><span class="sxs-lookup"><span data-stu-id="78d21-114">The compatibility depends on the type category of `typename`.</span></span> <span data-ttu-id="78d21-115">В следующей таблице показано, как определяется совместимость.</span><span class="sxs-lookup"><span data-stu-id="78d21-115">The following table shows how compatibility is determined.</span></span>  
  
|<span data-ttu-id="78d21-116">Категория типа `typename`</span><span class="sxs-lookup"><span data-stu-id="78d21-116">Type category of `typename`</span></span>|<span data-ttu-id="78d21-117">Критерий совместимости</span><span class="sxs-lookup"><span data-stu-id="78d21-117">Compatibility criterion</span></span>|  
|---------------------------------|-----------------------------|  
|<span data-ttu-id="78d21-118">Класс</span><span class="sxs-lookup"><span data-stu-id="78d21-118">Class</span></span>|<span data-ttu-id="78d21-119">`objectexpression` типа `typename` или наследует от `typename`</span><span class="sxs-lookup"><span data-stu-id="78d21-119">`objectexpression` is of type `typename` or inherits from `typename`</span></span>|  
|<span data-ttu-id="78d21-120">Структура</span><span class="sxs-lookup"><span data-stu-id="78d21-120">Structure</span></span>|<span data-ttu-id="78d21-121">`objectexpression` типа `typename`</span><span class="sxs-lookup"><span data-stu-id="78d21-121">`objectexpression` is of type `typename`</span></span>|  
|<span data-ttu-id="78d21-122">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="78d21-122">Interface</span></span>|<span data-ttu-id="78d21-123">`objectexpression` реализует `typename` или наследует от класса, реализующего `typename`</span><span class="sxs-lookup"><span data-stu-id="78d21-123">`objectexpression` implements `typename` or inherits from a class that implements `typename`</span></span>|  
  
 <span data-ttu-id="78d21-124">Если тип времени выполнения `objectexpression` удовлетворяет критерию совместимости, `result` является `True`.</span><span class="sxs-lookup"><span data-stu-id="78d21-124">If the run-time type of `objectexpression` satisfies the compatibility criterion, `result` is `True`.</span></span> <span data-ttu-id="78d21-125">В противном случае `result` является `False`.</span><span class="sxs-lookup"><span data-stu-id="78d21-125">Otherwise, `result` is `False`.</span></span>  <span data-ttu-id="78d21-126">Если `objectexpression` имеет значение null, то `TypeOf`...`Is` возвращает `False`, а ...`IsNot` возвращает `True`.</span><span class="sxs-lookup"><span data-stu-id="78d21-126">If `objectexpression` is null, then `TypeOf`...`Is` returns `False`, and ...`IsNot` returns `True`.</span></span>  
  
 <span data-ttu-id="78d21-127">`TypeOf` всегда используется с ключевым словом `Is` для создания выражения `TypeOf`...`Is` или с ключевым словом `IsNot` для создания выражения `TypeOf`...`IsNot`.</span><span class="sxs-lookup"><span data-stu-id="78d21-127">`TypeOf` is always used with the `Is` keyword to construct a `TypeOf`...`Is` expression, or with the `IsNot` keyword to construct a `TypeOf`...`IsNot` expression.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78d21-128">Пример</span><span class="sxs-lookup"><span data-stu-id="78d21-128">Example</span></span>  
 <span data-ttu-id="78d21-129">В следующем примере выражение `TypeOf`...`Is` используется для проверки на совместимость типов двух переменных ссылок на объекты с различными типами данных.</span><span class="sxs-lookup"><span data-stu-id="78d21-129">The following example uses `TypeOf`...`Is` expressions to test the type compatibility of two object reference variables with various data types.</span></span>  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 <span data-ttu-id="78d21-130">Переменная `refInteger` имеет тип времени выполнения `Integer`.</span><span class="sxs-lookup"><span data-stu-id="78d21-130">The variable `refInteger` has a run-time type of `Integer`.</span></span> <span data-ttu-id="78d21-131">Она совместима с `Integer`, но не с `Double`.</span><span class="sxs-lookup"><span data-stu-id="78d21-131">It is compatible with `Integer` but not with `Double`.</span></span> <span data-ttu-id="78d21-132">Переменная `refForm` имеет тип времени выполнения <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="78d21-132">The variable `refForm` has a run-time type of <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="78d21-133">Она совместима с <xref:System.Windows.Forms.Form>, так как это ее тип, с <xref:System.Windows.Forms.Control>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.Windows.Forms.Control>, и с <xref:System.ComponentModel.IComponent>, так как <xref:System.Windows.Forms.Form> наследует от <xref:System.ComponentModel.Component>, который реализует <xref:System.ComponentModel.IComponent>.</span><span class="sxs-lookup"><span data-stu-id="78d21-133">It is compatible with <xref:System.Windows.Forms.Form> because that is its type, with <xref:System.Windows.Forms.Control> because <xref:System.Windows.Forms.Form> inherits from <xref:System.Windows.Forms.Control>, and with <xref:System.ComponentModel.IComponent> because <xref:System.Windows.Forms.Form> inherits from <xref:System.ComponentModel.Component>, which implements <xref:System.ComponentModel.IComponent>.</span></span> <span data-ttu-id="78d21-134">Однако `refForm` несовместима с <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="78d21-134">However, `refForm` is not compatible with <xref:System.Windows.Forms.Label>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d21-135">См. также</span><span class="sxs-lookup"><span data-stu-id="78d21-135">See also</span></span>
- [<span data-ttu-id="78d21-136">Оператор Is</span><span class="sxs-lookup"><span data-stu-id="78d21-136">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="78d21-137">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="78d21-137">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="78d21-138">Операторы сравнения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78d21-138">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="78d21-139">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="78d21-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="78d21-140">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="78d21-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="78d21-141">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="78d21-141">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
