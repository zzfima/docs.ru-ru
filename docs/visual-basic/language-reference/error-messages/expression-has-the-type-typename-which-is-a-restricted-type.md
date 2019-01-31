---
title: Выражение имеет тип <typename> который является ограниченным и не может использоваться для доступа к членам, унаследованным от Object или ValueType
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 6d366ec750ea5a4505ae5ea618e27f47406ba959
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274050"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a>Выражение имеет тип "\<typename >" которого является ограниченным типом и не может использоваться для доступа к членам, унаследованным из «Object» или «ValueType»
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
