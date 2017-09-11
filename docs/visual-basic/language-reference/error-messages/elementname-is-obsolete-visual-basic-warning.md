---
title: "&quot;&lt;elementname&gt;&quot; является устаревшим (предупреждение Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40008
- bc40008
dev_langs:
- VB
helpviewer_keywords:
- BC40008
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 77708f052f7aec7a5da2b24605ba3bd794f83979
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="39ltelementnamegt39-is-obsolete-visual-basic-warning"></a><span data-ttu-id="78b3a-102">"&lt;elementname&gt;" является устаревшим (предупреждение Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78b3a-102">&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)</span></span>
<span data-ttu-id="78b3a-103">Оператор пытается получить доступ к элементу программирования, который был помечен с <xref:System.ObsoleteAttribute>атрибут и следует рассматривать ее как предупреждение.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="78b3a-103">A statement attempts to access a programming element which has been marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as a warning.</span></span>  
  
 <span data-ttu-id="78b3a-104">Можно пометить любой элемент программирования как более не используется путем применения <xref:System.ObsoleteAttribute>к его.</xref:System.ObsoleteAttribute></span><span class="sxs-lookup"><span data-stu-id="78b3a-104">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="78b3a-105">После этого можно задать атрибут <xref:System.ObsoleteAttribute.IsError%2A>значение `True` или `False`.</xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="78b3a-105">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="78b3a-106">Если задать значение `True`, компилятор будет рассматривать попытку использовать элемент как ошибку.</span><span class="sxs-lookup"><span data-stu-id="78b3a-106">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="78b3a-107">Если задать значение `False`или оставить значение по умолчанию `False`, то при попытке использовать элемент компилятор выдаст предупреждение.</span><span class="sxs-lookup"><span data-stu-id="78b3a-107">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="78b3a-108">По умолчанию это сообщение является предупреждением, поскольку <xref:System.ObsoleteAttribute.IsError%2A>свойство <xref:System.ObsoleteAttribute>— `False`.</xref:System.ObsoleteAttribute> </xref:System.ObsoleteAttribute.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="78b3a-108">By default, this message is a warning, because the <xref:System.ObsoleteAttribute.IsError%2A> property of <xref:System.ObsoleteAttribute> is `False`.</span></span> <span data-ttu-id="78b3a-109">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="78b3a-109">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="78b3a-110">**Идентификатор ошибки:** BC40008</span><span class="sxs-lookup"><span data-stu-id="78b3a-110">**Error ID:** BC40008</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="78b3a-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="78b3a-111">To correct this error</span></span>  
  
-   <span data-ttu-id="78b3a-112">Убедитесь, что в ссылке исходного кода имя элемента указано правильно.</span><span class="sxs-lookup"><span data-stu-id="78b3a-112">Ensure that the source-code reference is spelling the element name correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78b3a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="78b3a-113">See Also</span></span>  
 [<span data-ttu-id="78b3a-114">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="78b3a-114">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

