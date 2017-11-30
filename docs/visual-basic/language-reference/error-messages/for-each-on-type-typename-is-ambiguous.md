---
title: "&#39; Для каждого &#39; на тип &#39; &lt;typename&gt;&#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39; System.Collections.Generic.IEnumerable (Of T) &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords: BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39; Для каждого &#39; на тип &#39; &lt;typename&gt;&#39; является неоднозначным, поскольку тип реализует несколько экземпляров &#39; System.Collections.Generic.IEnumerable (Of T) &#39;
Объект `For Each` инструкция указывает переменная-итератор содержит несколько <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод.  
  
 Итератор переменная должна иметь тип, реализующий <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> интерфейса в одном из `Collections` пространства имен [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]. Это класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа для каждого построения. Если класс, который делает это используется для переменной итератора, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A> метод. В этом случае [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] нельзя выбрать вызываемый метод.  
  
 **Идентификатор ошибки:** BC32096  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной итератора в определении интерфейса <xref:System.Collections.IEnumerable.GetEnumerator%2A> метода, которые вы хотите использовать.  
  
## <a name="see-also"></a>См. также  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
