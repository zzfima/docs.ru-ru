---
title: Оператор GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592153"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="88c37-102">Оператор GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88c37-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="88c37-103">Возвращает объект <xref:System.Type> для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="88c37-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="88c37-104">Объект <xref:System.Type> предоставляет сведения о типе, например его свойствах, методах и событиях.</span><span class="sxs-lookup"><span data-stu-id="88c37-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c37-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88c37-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="88c37-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="88c37-106">Parameters</span></span>  
  
|<span data-ttu-id="88c37-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="88c37-107">Parameter</span></span>|<span data-ttu-id="88c37-108">Описание</span><span class="sxs-lookup"><span data-stu-id="88c37-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="88c37-109">Имя типа, для которого требуется получить сведения.</span><span class="sxs-lookup"><span data-stu-id="88c37-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88c37-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="88c37-110">Remarks</span></span>  
 <span data-ttu-id="88c37-111">Оператор `GetType` возвращает объект <xref:System.Type> для указанного `typename`.</span><span class="sxs-lookup"><span data-stu-id="88c37-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="88c37-112">Имя любого определенного типа можно передать в `typename`.</span><span class="sxs-lookup"><span data-stu-id="88c37-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="88c37-113">Это поведение характеризуется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="88c37-113">This includes the following:</span></span>  
  
- <span data-ttu-id="88c37-114">Любой тип данных Visual Basic, например `Boolean` или `Date`.</span><span class="sxs-lookup"><span data-stu-id="88c37-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="88c37-115">Любой .NET Framework класс, структура, модуль или интерфейс, например <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88c37-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="88c37-116">Любой класс, структура, модуль или интерфейс, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="88c37-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="88c37-117">Любой массив, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="88c37-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="88c37-118">Любой делегат, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="88c37-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="88c37-119">Любое перечисление, определенное Visual Basic, .NET Framework или вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="88c37-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="88c37-120">Если требуется получить объект типа объектной переменной, используйте метод <xref:System.Type.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88c37-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="88c37-121">Оператор `GetType` может быть полезен в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="88c37-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="88c37-122">Необходимо получить доступ к метаданным для типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88c37-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="88c37-123">Объект <xref:System.Type> предоставляет метаданные, такие как члены типов и сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="88c37-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="88c37-124">Это необходимо, например, для отражения сборки.</span><span class="sxs-lookup"><span data-stu-id="88c37-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="88c37-125">Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="88c37-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="88c37-126">Необходимо сравнить две ссылки на объект, чтобы определить, ссылаются ли они на экземпляры одного типа.</span><span class="sxs-lookup"><span data-stu-id="88c37-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="88c37-127">В противном случае `GetType` возвращает ссылки на один и тот же объект <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="88c37-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88c37-128">Пример</span><span class="sxs-lookup"><span data-stu-id="88c37-128">Example</span></span>  
 <span data-ttu-id="88c37-129">В следующих примерах показано использование оператора `GetType`.</span><span class="sxs-lookup"><span data-stu-id="88c37-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="88c37-130">См. также</span><span class="sxs-lookup"><span data-stu-id="88c37-130">See also</span></span>

- [<span data-ttu-id="88c37-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="88c37-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="88c37-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="88c37-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="88c37-133">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="88c37-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
