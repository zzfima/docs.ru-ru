---
title: '&#39;Для каждого&#39; в типе &#39; &lt;typename&gt; &#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39;System.Collections.Generic.IEnumerable (Of T)&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: 7fd779ba34afa2a59fa6c42971597df8ce01495a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597350"
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39;Для каждого&#39; в типе &#39; &lt;typename&gt; &#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39;System.Collections.Generic.IEnumerable (Of T)&#39;
Объект `For Each` инструкция указывает переменная-итератор с более чем одним <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.  
  
 Переменная-итератор должен иметь тип, который реализует <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейса в одном из `Collections` пространства имен [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Это класс может реализовать более одного сконструированный универсальный интерфейс, используя разные аргументы типа для каждого построения. Если класс, который делает это используется для переменной-итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод. В этом случае Visual Basic не может выбрать метод для вызова.  
  
 **Идентификатор ошибки:** BC32096  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной итератора, как определить интерфейс <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, вы хотите использовать.  
  
## <a name="see-also"></a>См. также
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
