---
title: Переменная &#39; &lt;variablename&gt; &#39; была использована прежде чем ей было присвоено значение
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="74a3d-102">Переменная &#39; &lt;variablename&gt; &#39; была использована прежде чем ей было присвоено значение</span><span class="sxs-lookup"><span data-stu-id="74a3d-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="74a3d-103">Переменной "\<variablename >" используется, прежде чем ей было присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="74a3d-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="74a3d-104">Во время выполнения может возникнуть исключение "пустая ссылка".</span><span class="sxs-lookup"><span data-stu-id="74a3d-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="74a3d-105">Приложение имеет по крайней мере один возможный путь во всем коде, который считывает значение переменной перед к нему было назначено значение.</span><span class="sxs-lookup"><span data-stu-id="74a3d-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="74a3d-106">Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных.</span><span class="sxs-lookup"><span data-stu-id="74a3d-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="74a3d-107">Для ссылочного типа данных, что значение по умолчанию — [ничего не](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="74a3d-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="74a3d-108">Чтение переменной ссылки, которая имеет значение `Nothing` , в некоторых случаях может привести к исключению <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="74a3d-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="74a3d-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="74a3d-109">By default, this message is a warning.</span></span> <span data-ttu-id="74a3d-110">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="74a3d-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="74a3d-111">**Идентификатор ошибки:** BC42104</span><span class="sxs-lookup"><span data-stu-id="74a3d-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="74a3d-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="74a3d-112">To correct this error</span></span>  
  
-   <span data-ttu-id="74a3d-113">Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается оператору, используемого для чтения.</span><span class="sxs-lookup"><span data-stu-id="74a3d-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="74a3d-114">Чтобы гарантировать, что переменная всегда имеет допустимое значение можно инициализировать его в рамках его объявления.</span><span class="sxs-lookup"><span data-stu-id="74a3d-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="74a3d-115">В разделе «Инициализация» в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="74a3d-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a3d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="74a3d-116">See Also</span></span>  
 [<span data-ttu-id="74a3d-117">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="74a3d-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="74a3d-118">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="74a3d-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="74a3d-119">Устранение неполадок, связанных с переменными</span><span class="sxs-lookup"><span data-stu-id="74a3d-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
