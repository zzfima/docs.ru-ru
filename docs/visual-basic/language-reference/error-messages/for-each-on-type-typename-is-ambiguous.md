---
title: Оператор For Each для типа <typename> неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: af2340e8e514391503d5f9b706d13ba93336698e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662115"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a><span data-ttu-id="09db9-102">«For Each» в типе "\<typename >" является неоднозначным, поскольку этот тип реализует несколько экземпляров «System.Collections.Generic.IEnumerable (Of T)»</span><span class="sxs-lookup"><span data-stu-id="09db9-102">'For Each' on type '\<typename>' is ambiguous because the type implements multiple instantiations of 'System.Collections.Generic.IEnumerable(Of T)'</span></span>
<span data-ttu-id="09db9-103">Объект `For Each` инструкция указывает переменная-итератор с более чем одним <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="09db9-103">A `For Each` statement specifies an iterator variable that has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span>  
  
 <span data-ttu-id="09db9-104">Переменная-итератор должен иметь тип, который реализует <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейса в одном из `Collections` пространства имен [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09db9-104">The iterator variable must be of a type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface in one of the `Collections` namespaces of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="09db9-105">Это класс может реализовать более одного сконструированный универсальный интерфейс, используя разные аргументы типа для каждого построения.</span><span class="sxs-lookup"><span data-stu-id="09db9-105">It is possible for a class to implement more than one constructed generic interface, using a different type argument for each construction.</span></span> <span data-ttu-id="09db9-106">Если класс, который делает это используется для переменной-итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="09db9-106">If a class that does this is used for the iterator variable, that variable has more than one <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="09db9-107">В этом случае Visual Basic не может выбрать метод для вызова.</span><span class="sxs-lookup"><span data-stu-id="09db9-107">In such a case, Visual Basic cannot choose which method to call.</span></span>  
  
 <span data-ttu-id="09db9-108">**Идентификатор ошибки:** BC32096</span><span class="sxs-lookup"><span data-stu-id="09db9-108">**Error ID:** BC32096</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="09db9-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="09db9-109">To correct this error</span></span>  
  
- <span data-ttu-id="09db9-110">Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной итератора, как определить интерфейс <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="09db9-110">Use [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) to cast the iterator variable type to the interface defining the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method you want to use.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09db9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="09db9-111">See also</span></span>

- [<span data-ttu-id="09db9-112">Оператор For Each...Next</span><span class="sxs-lookup"><span data-stu-id="09db9-112">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="09db9-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="09db9-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
