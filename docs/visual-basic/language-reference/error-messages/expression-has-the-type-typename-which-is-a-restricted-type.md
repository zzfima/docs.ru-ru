---
title: Выражение имеет тип &#39; &lt;typename&gt;&#39; который является ограниченным типом и не может использоваться для доступа к членам, унаследованным от &#39; объект &#39; или &#39; ValueType &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30742bd46ccd1a3e5a688ebd2621e2c8a3d50e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a><span data-ttu-id="08bdf-102">Выражение имеет тип &#39; &lt;typename&gt;&#39; который является ограниченным типом и не может использоваться для доступа к членам, унаследованным от &#39; объект &#39; или &#39; ValueType &#39;</span><span class="sxs-lookup"><span data-stu-id="08bdf-102">Expression has the type &#39;&lt;typename&gt;&#39; which is a restricted type and cannot be used to access members inherited from &#39;Object&#39; or &#39;ValueType&#39;</span></span>
<span data-ttu-id="08bdf-103">Выражение приводится к типу, который не может быть упакован в общеязыковой среде выполнения (CLR), но обращается к члену, для которого требуется упаковка.</span><span class="sxs-lookup"><span data-stu-id="08bdf-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="08bdf-104">*Упаковкой-преобразованием* называется обработка, необходимая для преобразования типа в `Object` или, в некоторых случаях, в <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="08bdf-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="08bdf-105">Общеязыковая среда выполнения не поддерживает упаковку определенных типов структуры, например <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, и <xref:System.TypedReference>.</span><span class="sxs-lookup"><span data-stu-id="08bdf-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="08bdf-106">Это выражение пытается использовать ограниченный тип для вызова метода, унаследованного от <xref:System.Object> или <xref:System.ValueType>, такие как <xref:System.Object.GetHashCode%2A> или <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="08bdf-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="08bdf-107">Для доступа к этому методу [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] выполняется преобразование неявная упаковка-преобразование, которое вызывает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="08bdf-107">To access this method, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="08bdf-108">**Идентификатор ошибки:** BC31393</span><span class="sxs-lookup"><span data-stu-id="08bdf-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08bdf-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="08bdf-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="08bdf-110">Найдите выражение, которое оценивается в указанный тип.</span><span class="sxs-lookup"><span data-stu-id="08bdf-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2.  <span data-ttu-id="08bdf-111">Найдите часть инструкции, который пытается вызвать метод, унаследованный от <xref:System.Object> или <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="08bdf-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3.  <span data-ttu-id="08bdf-112">Перепишите инструкцию, чтобы избежать вызова метода.</span><span class="sxs-lookup"><span data-stu-id="08bdf-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08bdf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="08bdf-113">See Also</span></span>  
 [<span data-ttu-id="08bdf-114">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="08bdf-114">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
