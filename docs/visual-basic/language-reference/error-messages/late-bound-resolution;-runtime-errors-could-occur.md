---
title: "Разрешение позднего связывания; Возможны ошибки времени выполнения | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
dev_langs:
- VB
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
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
ms.openlocfilehash: 3baf28a17077d255b42f38ade21ce6153c24e862
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="d87e7-102">Разрешение позднего связывания; возможно возникновение ошибок времени выполнения</span><span class="sxs-lookup"><span data-stu-id="d87e7-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="d87e7-103">Объект присваивается переменной, объявленной как [тип данных объекта](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d87e7-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="d87e7-104">При объявлении переменной как `Object`, компилятор должен выполнить *позднего связывания*, которое вызывает дополнительные операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d87e7-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="d87e7-105">Это также подвергает приложение риску возникновения ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d87e7-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="d87e7-106">Например, если присвоить <xref:System.Windows.Forms.Form>для `Object` переменной и затем пытаемся обратиться к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>свойство, среда выполнения создает <xref:System.MemberAccessException>поскольку <xref:System.Windows.Forms.Form>класс не предоставляет `NameTable` свойство.</xref:System.Windows.Forms.Form> </xref:System.MemberAccessException> </xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> </xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="d87e7-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="d87e7-107">При объявлении переменной определенного типа, компилятор может выполнять *раннее связывание* во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="d87e7-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="d87e7-108">Это позволяет повысить производительность, контролируемого доступа к членам определенного типа и лучшей читаемости кода.</span><span class="sxs-lookup"><span data-stu-id="d87e7-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="d87e7-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="d87e7-109">By default, this message is a warning.</span></span> <span data-ttu-id="d87e7-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d87e7-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d87e7-111">**Идентификатор ошибки:** BC42017</span><span class="sxs-lookup"><span data-stu-id="d87e7-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d87e7-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d87e7-112">To correct this error</span></span>  
  
-   <span data-ttu-id="d87e7-113">Если возможно объявите переменную для определенного типа.</span><span class="sxs-lookup"><span data-stu-id="d87e7-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d87e7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d87e7-114">See Also</span></span>  
 <span data-ttu-id="d87e7-115">[Раннее и позднее связывание](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="d87e7-115">[Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="d87e7-116"> [Объявление объектной переменной](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span><span class="sxs-lookup"><span data-stu-id="d87e7-116"> [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)</span></span>
