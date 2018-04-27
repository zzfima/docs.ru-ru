---
title: '&#39;Для каждого&#39; типа &#39; &lt;typename&gt; &#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 81cb37cc4b61fa96e64f59150d95356b2fb0a355
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a><span data-ttu-id="e8188-102">&#39;Для каждого&#39; типа &#39; &lt;typename&gt; &#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39;System.Collections.Generic.IEnumerable (Of T)&#39;</span><span class="sxs-lookup"><span data-stu-id="e8188-102">&#39;For Each&#39; on type &#39;&lt;typename&gt;&#39; is ambiguous because the type implements multiple instantiations of &#39;System.Collections.Generic.IEnumerable(Of T)&#39;</span></span>
<span data-ttu-id="e8188-103">Объект `For Each` инструкция указывает переменная-итератор содержит несколько <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e8188-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="e8188-104">Итератор переменная должна иметь тип, реализующий <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейса в одном из `Collections` пространства имен [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8188-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="e8188-105">Это класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа для каждого построения.</span><span class="sxs-lookup"><span data-stu-id="e8188-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="e8188-106">Если класс, который делает это используется для переменной итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e8188-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="e8188-107">В этом случае Visual Basic нельзя выбрать вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="e8188-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="e8188-108">**Идентификатор ошибки:** BC32096</span><span class="sxs-lookup"><span data-stu-id="e8188-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8188-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e8188-109">To correct this error</span></span>  
  
-   <span data-ttu-id="e8188-110">Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной итератора в определении интерфейса <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="e8188-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8188-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e8188-111">See Also</span></span>  
 [<span data-ttu-id="e8188-112">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="e8188-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="e8188-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e8188-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
