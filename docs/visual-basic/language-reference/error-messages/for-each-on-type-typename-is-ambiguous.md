---
title: "«Для каждого» в типе &quot;&lt;typename&gt;&quot; является неоднозначным, поскольку тип реализует несколько экземпляров «System.Collections.Generic.IEnumerable (Of T)» | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
dev_langs:
- VB
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6177b48cdc3bc4085cecb6d73c164684ef1c0bc6
ms.lasthandoff: 03/13/2017

---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>«Для каждого» в типе "&lt;typename&gt;" является неоднозначным, поскольку тип реализует несколько экземпляров «System.Collections.Generic.IEnumerable (Of T)»
Объект `For Each` инструкция указывает переменной итератора, который имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
 Итератор переменная должна иметь тип, который реализует <xref:System.Collections.IEnumerable?displayProperty=fullName>или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>интерфейса в одном из `Collections` пространства имен [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> </xref:System.Collections.IEnumerable?displayProperty=fullName> Это класс может реализовывать несколько сконструированных универсальных интерфейсов, используя разные аргументы типа для каждого построения. Если для переменной итератора используется класс, который делает это, эта переменная имеет более одного <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод.</xref:System.Collections.IEnumerable.GetEnumerator%2A> В этом случае [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] нельзя выбрать вызываемый метод.  
  
 **Идентификатор ошибки:** BC32096  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) или [оператор TryCast](../../../visual-basic/language-reference/operators/trycast-operator.md) для приведения типа переменной-итератора к определению интерфейса <xref:System.Collections.IEnumerable.GetEnumerator%2A>метода, которые вы хотите использовать.</xref:System.Collections.IEnumerable.GetEnumerator%2A>  
  
## <a name="see-also"></a>См. также  
 [Для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Интерфейсы](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
