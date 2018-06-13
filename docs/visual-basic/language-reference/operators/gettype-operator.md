---
title: Оператор GetType (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 581f576222eb149aede841a5da7a0e5f38c77b58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603851"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="80d6e-102">Оператор GetType (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80d6e-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="80d6e-103">Возвращает <xref:System.Type> объекта для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="80d6e-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="80d6e-104"><xref:System.Type> Объект предоставляет сведения о типе, например его свойства, методы и события.</span><span class="sxs-lookup"><span data-stu-id="80d6e-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80d6e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80d6e-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80d6e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="80d6e-106">Parameters</span></span>  
  
|<span data-ttu-id="80d6e-107">Параметр</span><span class="sxs-lookup"><span data-stu-id="80d6e-107">Parameter</span></span>|<span data-ttu-id="80d6e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="80d6e-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="80d6e-109">Имя типа, для которого требуется получить сведения.</span><span class="sxs-lookup"><span data-stu-id="80d6e-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80d6e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="80d6e-110">Remarks</span></span>  
 <span data-ttu-id="80d6e-111">`GetType` Оператор возвращает <xref:System.Type> для указанного `typename`.</span><span class="sxs-lookup"><span data-stu-id="80d6e-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="80d6e-112">Можно передать имя любого типа в `typename`.</span><span class="sxs-lookup"><span data-stu-id="80d6e-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="80d6e-113">Это поведение характеризуется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="80d6e-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="80d6e-114">Тип данных Visual Basic, например `Boolean` или `Date`.</span><span class="sxs-lookup"><span data-stu-id="80d6e-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="80d6e-115">Все платформы .NET Framework класса, структуры, модуля или интерфейса, такие как <xref:System.ArgumentException?displayProperty=nameWithType> или <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80d6e-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="80d6e-116">Любой класс, структура, модуль или интерфейс, определяемый приложением.</span><span class="sxs-lookup"><span data-stu-id="80d6e-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="80d6e-117">Любой массив, определяемый приложением.</span><span class="sxs-lookup"><span data-stu-id="80d6e-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="80d6e-118">Любой делегат, определяемый приложением.</span><span class="sxs-lookup"><span data-stu-id="80d6e-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="80d6e-119">Любое перечисление, определенное в Visual Basic .NET Framework и приложения.</span><span class="sxs-lookup"><span data-stu-id="80d6e-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="80d6e-120">Если вы хотите получить объект типа переменной объекта, используйте <xref:System.Type.GetType%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="80d6e-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="80d6e-121">`GetType` Оператор может быть полезно в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="80d6e-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="80d6e-122">Для доступа к метаданные для типа во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="80d6e-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="80d6e-123"><xref:System.Type> Предоставляет метаданные, такие как члены типа и сведения о развертывании.</span><span class="sxs-lookup"><span data-stu-id="80d6e-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="80d6e-124">Это необходимо, например, чтобы отобразить сборку.</span><span class="sxs-lookup"><span data-stu-id="80d6e-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="80d6e-125">Дополнительные сведения см. в разделе <xref:System.Reflection?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80d6e-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="80d6e-126">Вы хотите сравнить две ссылки на объект для просмотра, если они ссылаются на экземпляры того же типа.</span><span class="sxs-lookup"><span data-stu-id="80d6e-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="80d6e-127">Если они есть, `GetType` возвращает ссылки на один и тот же <xref:System.Type> объекта.</span><span class="sxs-lookup"><span data-stu-id="80d6e-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80d6e-128">Пример</span><span class="sxs-lookup"><span data-stu-id="80d6e-128">Example</span></span>  
 <span data-ttu-id="80d6e-129">В приведенных ниже примерах `GetType` оператор используется.</span><span class="sxs-lookup"><span data-stu-id="80d6e-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="80d6e-130">См. также</span><span class="sxs-lookup"><span data-stu-id="80d6e-130">See Also</span></span>  
 [<span data-ttu-id="80d6e-131">Порядок применения операторов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80d6e-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="80d6e-132">Список операторов, сгруппированных по функциональному назначению</span><span class="sxs-lookup"><span data-stu-id="80d6e-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="80d6e-133">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="80d6e-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
