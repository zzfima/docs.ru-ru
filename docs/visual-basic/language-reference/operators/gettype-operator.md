---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349548"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="f9d79-102">Оператор GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9d79-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="f9d79-103">Возвращает объект <xref:System.Type> для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="f9d79-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="f9d79-104">Объект <xref:System.Type> предоставляет сведения о типе, например его свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="f9d79-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9d79-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9d79-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9d79-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f9d79-106">Parameters</span></span>  
  
|<span data-ttu-id="f9d79-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="f9d79-107">Parameter</span></span>|<span data-ttu-id="f9d79-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f9d79-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="f9d79-109">Имя типа, для которого требуется получить сведения.</span><span class="sxs-lookup"><span data-stu-id="f9d79-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9d79-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="f9d79-110">Remarks</span></span>  
 <span data-ttu-id="f9d79-111">Оператор `GetType` возвращает объект <xref:System.Type> для указанного `typename`.</span><span class="sxs-lookup"><span data-stu-id="f9d79-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="f9d79-112">В `typename`можно передать имя любого определенного типа.</span><span class="sxs-lookup"><span data-stu-id="f9d79-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="f9d79-113">Это поведение характеризуется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="f9d79-113">This includes the following:</span></span>  
  
- <span data-ttu-id="f9d79-114">Любой тип данных Visual Basic, например `Boolean` или `Date`.</span><span class="sxs-lookup"><span data-stu-id="f9d79-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="f9d79-115">Любой .NET Framework класс, структура, модуль или интерфейс, например <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d79-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f9d79-116">Любой класс, структура, модуль или интерфейс, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="f9d79-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="f9d79-117">Любой массив, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="f9d79-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="f9d79-118">Любой делегат, определенный приложением.</span><span class="sxs-lookup"><span data-stu-id="f9d79-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="f9d79-119">Любое перечисление, определенное Visual Basic, .NET Framework или вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="f9d79-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="f9d79-120">Если требуется получить объект типа объектной переменной, используйте метод <xref:System.Type.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d79-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f9d79-121">Оператор `GetType` может быть полезен в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="f9d79-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="f9d79-122">Необходимо получить доступ к метаданным для типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f9d79-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="f9d79-123">Объект <xref:System.Type> предоставляет метаданные, такие как члены типов и сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="f9d79-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="f9d79-124">Это необходимо, например, для отражения сборки.</span><span class="sxs-lookup"><span data-stu-id="f9d79-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="f9d79-125">Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f9d79-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="f9d79-126">Необходимо сравнить две ссылки на объект, чтобы определить, ссылаются ли они на экземпляры одного типа.</span><span class="sxs-lookup"><span data-stu-id="f9d79-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="f9d79-127">В противном случае `GetType` возвращает ссылки на один и тот же объект <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="f9d79-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9d79-128">Пример</span><span class="sxs-lookup"><span data-stu-id="f9d79-128">Example</span></span>  
 <span data-ttu-id="f9d79-129">В следующих примерах показан используемый оператор `GetType`.</span><span class="sxs-lookup"><span data-stu-id="f9d79-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="f9d79-130">См. также</span><span class="sxs-lookup"><span data-stu-id="f9d79-130">See also</span></span>

- [<span data-ttu-id="f9d79-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9d79-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f9d79-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="f9d79-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f9d79-133">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="f9d79-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
