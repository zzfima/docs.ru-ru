---
title: "Свойство &quot;&lt;propertyname&gt;&quot; возвращает значение не для всех путей кода | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42107
- vbc42107
dev_langs:
- VB
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 64bacc2a2494160b3f9bbaec0915179f40735ef0
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="64b71-102">Свойство "&lt;propertyname&gt;" возвращает значение не для всех путей кода</span><span class="sxs-lookup"><span data-stu-id="64b71-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="64b71-103">Свойство "\<propertyname настроек" возвращает значение не для всех ветвей кода.</span><span class="sxs-lookup"><span data-stu-id="64b71-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="64b71-104">Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.</span><span class="sxs-lookup"><span data-stu-id="64b71-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="64b71-105">Свойство `Get` процедура имеет хотя бы один возможный путь во всем коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="64b71-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="64b71-106">Может возвращать значение из свойства `Get` процедура в любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="64b71-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="64b71-107">Присвойте значение имени свойства, а затем выполнить `Exit Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64b71-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="64b71-108">Присвойте значение имени свойства, а затем выполнить `End Get` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64b71-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="64b71-109">Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64b71-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="64b71-110">Если управление передается `Exit Property` или `End Get` и имя свойства не назначить любое значение `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="64b71-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="64b71-111">Дополнительные сведения см. в разделе «Поведение» в [инструкции Function](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="64b71-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="64b71-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="64b71-112">By default, this message is a warning.</span></span> <span data-ttu-id="64b71-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="64b71-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="64b71-114">**Идентификатор ошибки:** BC42107</span><span class="sxs-lookup"><span data-stu-id="64b71-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="64b71-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="64b71-115">To correct this error</span></span>  
  
-   <span data-ttu-id="64b71-116">Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.</span><span class="sxs-lookup"><span data-stu-id="64b71-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="64b71-117">Проще гарантировать, что каждое возвращение из процедуры возвращает значение, если всегда использовать `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64b71-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="64b71-118">После этого, последним оператором перед `End Get` должно быть `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="64b71-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64b71-119">См. также</span><span class="sxs-lookup"><span data-stu-id="64b71-119">See Also</span></span>  
 <span data-ttu-id="64b71-120">[Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="64b71-120">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="64b71-121"> [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="64b71-121"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="64b71-122"> [Оператор Get](../../../visual-basic/language-reference/statements/get-statement.md)</span><span class="sxs-lookup"><span data-stu-id="64b71-122"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)</span></span>
