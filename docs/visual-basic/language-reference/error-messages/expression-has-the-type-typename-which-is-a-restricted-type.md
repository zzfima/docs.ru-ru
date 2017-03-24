---
title: "Выражение имеет тип &quot;&lt;typename&gt;&quot; которого является ограниченным и не может использоваться для доступа к членам, унаследованным от &quot;Object&quot; или &quot;ValueType&quot; | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: aaedfd825889498159f92cbd1d615cc0064973d3
ms.lasthandoff: 03/13/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Выражение имеет тип "&lt;typename&gt;" которого является ограниченным и не может использоваться для доступа к членам, унаследованным от 'Object' или 'ValueType'
Выражение имеет тип, который не может быть упакован в общеязыковой среде выполнения (CLR), но обращается к члену, для которого требуется упаковка.  
  
 *Упаковка-преобразование* ссылается на обработку, необходимую для преобразования типа к `Object` или, в некоторых случаях <xref:System.ValueType>.</xref:System.ValueType> Общеязыковая среда выполнения не поддерживает упаковку определенных типов структуры, например <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>и <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator>  
  
 Это выражение пытается использовать ограниченный тип, для вызова метода, унаследованного от <xref:System.Object>или <xref:System.ValueType>, например <xref:System.Object.GetHashCode%2A>или <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> </xref:System.ValueType> </xref:System.Object> Для доступа к этому методу [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выполняется преобразование неявная упаковка-преобразование, которое вызывает эту ошибку.  
  
 **Идентификатор ошибки:** BC31393  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Найдите выражение, которое оценивается в указанный тип.  
  
2.  Найдите часть оператора, который пытается вызвать метод, унаследованный от <xref:System.Object>или <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object>  
  
3.  Перепишите инструкцию, чтобы избежать вызова метода.  
  
## <a name="see-also"></a>См. также  
 [Явные и неявные преобразования](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
