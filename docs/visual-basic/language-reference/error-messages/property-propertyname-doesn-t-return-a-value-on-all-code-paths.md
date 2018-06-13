---
title: Свойство &#39; &lt;propertyname&gt; &#39; &#39;t возвращает значение во всех путях кода
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 72bc7e45cadd2528f29c88bf6e80ee5f381052dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594218"
---
# <a name="property-39ltpropertynamegt39-doesn39t-return-a-value-on-all-code-paths"></a><span data-ttu-id="cf66d-102">Свойство &#39; &lt;propertyname&gt; &#39; &#39;t возвращает значение во всех путях кода</span><span class="sxs-lookup"><span data-stu-id="cf66d-102">Property &#39;&lt;propertyname&gt;&#39; doesn&#39;t return a value on all code paths</span></span>
<span data-ttu-id="cf66d-103">Свойство "\<имя_свойства >" не возвращает значение во всех путях кода.</span><span class="sxs-lookup"><span data-stu-id="cf66d-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="cf66d-104">Во время выполнения может возникнуть исключение, связанное с пустой ссылкой, когда используется результат.</span><span class="sxs-lookup"><span data-stu-id="cf66d-104">A null reference exception could occur at run time when the result is used.</span></span>  
  
 <span data-ttu-id="cf66d-105">Свойство `Get` процедура имеет по крайней мере один возможный путь во всем коде, который не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="cf66d-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>  
  
 <span data-ttu-id="cf66d-106">Может возвращать значение из свойства `Get` процедура в любой из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="cf66d-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>  
  
-   <span data-ttu-id="cf66d-107">Присвойте значение имени свойства, а затем выполнить `Exit Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cf66d-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>  
  
-   <span data-ttu-id="cf66d-108">Присвойте значение имени свойства, а затем выполнить `End Get` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cf66d-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>  
  
-   <span data-ttu-id="cf66d-109">Включите значение в [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cf66d-109">Include the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="cf66d-110">Если управление передается `Exit Property` или `End Get` и имя свойства, не назначенным любое значение `Get` процедура возвращает значение по умолчанию для типа данных свойства.</span><span class="sxs-lookup"><span data-stu-id="cf66d-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="cf66d-111">Дополнительные сведения см. в разделе «Поведение» в [Function, инструкция](../../../visual-basic/language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cf66d-111">For more information, see "Behavior" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="cf66d-112">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="cf66d-112">By default, this message is a warning.</span></span> <span data-ttu-id="cf66d-113">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="cf66d-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cf66d-114">**Идентификатор ошибки:** BC42107</span><span class="sxs-lookup"><span data-stu-id="cf66d-114">**Error ID:** BC42107</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf66d-115">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cf66d-115">To correct this error</span></span>  
  
-   <span data-ttu-id="cf66d-116">Проверьте логику потока управления и убедитесь, что можно присвоить значение перед каждым оператором, вызывающим возврат.</span><span class="sxs-lookup"><span data-stu-id="cf66d-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>  
  
     <span data-ttu-id="cf66d-117">Проще гарантировать, что каждый возврата из процедуры возвращает значение, если всегда использовать `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cf66d-117">It is easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="cf66d-118">После этого, последней инструкцией перед `End Get` должно быть `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="cf66d-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf66d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cf66d-119">See Also</span></span>  
 [<span data-ttu-id="cf66d-120">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="cf66d-120">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="cf66d-121">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="cf66d-121">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="cf66d-122">Оператор Get</span><span class="sxs-lookup"><span data-stu-id="cf66d-122">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
