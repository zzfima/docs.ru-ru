---
title: "Разрешение позднего связывания; возможно возникновение ошибок времени выполнения"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords: BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d01164914b484ef689654f048a8743f3c2eb669
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a><span data-ttu-id="0eab9-102">Разрешение позднего связывания; возможно возникновение ошибок времени выполнения</span><span class="sxs-lookup"><span data-stu-id="0eab9-102">Late bound resolution; runtime errors could occur</span></span>
<span data-ttu-id="0eab9-103">Объект присваивается переменной, объявленной [тип данных объекта](../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="0eab9-103">An object is assigned to a variable declared to be of the [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="0eab9-104">При объявлении переменной как `Object`, компилятор должен осуществить *позднего связывания*, что вызывает дополнительные операции во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0eab9-104">When you declare a variable as `Object`, the compiler must perform *late binding*, which causes extra operations at run time.</span></span> <span data-ttu-id="0eab9-105">Это также подвергает приложение риску возникновения ошибок времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="0eab9-105">It also exposes your application to potential run-time errors.</span></span> <span data-ttu-id="0eab9-106">Например, если назначить <xref:System.Windows.Forms.Form> для `Object` переменной и попытаться получить доступ к <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> свойства, среда выполнения создает <xref:System.MemberAccessException> из-за <xref:System.Windows.Forms.Form> класс не предоставляет `NameTable` свойство.</span><span class="sxs-lookup"><span data-stu-id="0eab9-106">For example, if you assign a <xref:System.Windows.Forms.Form> to the `Object` variable and then try to access the <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> property, the runtime throws a <xref:System.MemberAccessException> because the <xref:System.Windows.Forms.Form> class does not expose a `NameTable` property.</span></span>  
  
 <span data-ttu-id="0eab9-107">При объявлении переменной определенного типа, компилятор может выполнять *раннее связывание* во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="0eab9-107">If you declare the variable to be of a specific type, the compiler can perform *early binding* at compile time.</span></span> <span data-ttu-id="0eab9-108">Это позволяет повысить производительность, управляемого доступа к членам определенного типа и удобочитаемости кода.</span><span class="sxs-lookup"><span data-stu-id="0eab9-108">This results in improved performance, controlled access to the members of the specific type, and better readability of your code.</span></span>  
  
 <span data-ttu-id="0eab9-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="0eab9-109">By default, this message is a warning.</span></span> <span data-ttu-id="0eab9-110">Сведения о сокрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="0eab9-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="0eab9-111">**Идентификатор ошибки:** BC42017</span><span class="sxs-lookup"><span data-stu-id="0eab9-111">**Error ID:** BC42017</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0eab9-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0eab9-112">To correct this error</span></span>  
  
-   <span data-ttu-id="0eab9-113">Если это возможно объявите переменную определенного типа.</span><span class="sxs-lookup"><span data-stu-id="0eab9-113">If possible, declare the variable to be of a specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eab9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0eab9-114">See Also</span></span>  
 [<span data-ttu-id="0eab9-115">Раннее и позднее связывание</span><span class="sxs-lookup"><span data-stu-id="0eab9-115">Early and Late Binding</span></span>](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [<span data-ttu-id="0eab9-116">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="0eab9-116">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
