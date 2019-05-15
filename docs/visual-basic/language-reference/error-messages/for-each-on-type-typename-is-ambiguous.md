---
title: Оператор For Each для типа <typename> неоднозначен, поскольку тип реализует несколько экземпляров System.Collections.Generic.IEnumerable (Of T)
ms.date: 07/20/2015
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
ms.openlocfilehash: bdfb6e9b1332db1f049bb2575e97215026efe0dd
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591767"
---
# <a name="for-each-on-type-typename-is-ambiguous-because-the-type-implements-multiple-instantiations-of-systemcollectionsgenericienumerableof-t"></a>«For Each» в типе "\<typename >" является неоднозначным, поскольку этот тип реализует несколько экземпляров «System.Collections.Generic.IEnumerable (Of T)»
Объект `For Each` инструкция указывает переменная-итератор с более чем одним <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.  
  
 Переменная-итератор должен иметь тип, который реализует <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейса в одном из `Collections` пространств имен платформы .NET Framework. Это класс может реализовать более одного сконструированный универсальный интерфейс, используя разные аргументы типа для каждого построения. Если класс, который делает это используется для переменной-итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод. В этом случае Visual Basic не может выбрать метод для вызова.  
  
 **Идентификатор ошибки:** BC32096  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной итератора, как определить интерфейс <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод, вы хотите использовать.  
  
## <a name="see-also"></a>См. также

- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
