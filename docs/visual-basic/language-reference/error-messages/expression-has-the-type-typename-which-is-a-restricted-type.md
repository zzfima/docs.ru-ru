---
title: Выражение имеет тип &#39; &lt;typename&gt; &#39; которого является ограниченным типом и не может использоваться для доступа к членам, унаследованным от &#39;объект&#39; или &#39;ValueType&#39;
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: d44b9a29f0848508d8cd814e857d9b01819ce7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535961"
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Выражение имеет тип &#39; &lt;typename&gt; &#39; которого является ограниченным типом и не может использоваться для доступа к членам, унаследованным от &#39;объект&#39; или &#39;ValueType&#39;
Выражение, результатом которого является тип, который не может быть упакован-преобразован средой общеязыковой среды выполнения (CLR), но обращается к члену, необходима упаковка.  
  
 *Упаковкой-преобразованием* называется обработка, необходимая для преобразования типа в `Object` или, в некоторых случаях, в <xref:System.ValueType>. Среда CLR не поддерживает упаковку определенных типов структуры, например <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, и <xref:System.TypedReference>.  
  
 Это выражение пытается выполнить вызов метода, унаследованного от ограниченного типа <xref:System.Object> или <xref:System.ValueType>, такие как <xref:System.Object.GetHashCode%2A> или <xref:System.Object.ToString%2A>. Для доступа к этому методу, Visual Basic выполняется преобразование неявная упаковка-преобразование, которое вызывает эту ошибку.  
  
 **Идентификатор ошибки:** BC31393  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Найдите выражение, которое оценивается в указанный тип.  
  
2.  Найдите часть инструкции, в которой предпринимается попытка вызова метода, унаследованного от <xref:System.Object> или <xref:System.ValueType>.  
  
3.  Перепишите инструкцию, чтобы избежать вызова метода.  
  
## <a name="see-also"></a>См. также
- [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
