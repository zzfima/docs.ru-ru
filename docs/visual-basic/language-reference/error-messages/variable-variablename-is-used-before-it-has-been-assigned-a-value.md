---
title: "Переменной &quot;&lt;variablename&gt;&quot; используется до присвоено значение | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
ms.openlocfilehash: dfc924ebbebb8b20654156b8871684dcfad6848a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="ed6a1-102">Переменной "&lt;variablename&gt;' используется до присвоено значение</span><span class="sxs-lookup"><span data-stu-id="ed6a1-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="ed6a1-103">Переменной "\<variablename настроек ' используется до присвоено значение.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="ed6a1-104">Во время выполнения может возникнуть исключение "пустая ссылка".</span><span class="sxs-lookup"><span data-stu-id="ed6a1-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="ed6a1-105">Приложение имеет по крайней мере один возможный путь в коде, которая считывает значение переменной, прежде чем он будет присвоено любое значение.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="ed6a1-106">Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="ed6a1-107">Для ссылочного типа данных, что значение по умолчанию — [ничего не](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="ed6a1-108">Чтение переменной ссылки, которая имеет значение `Nothing` может привести к <xref:System.NullReferenceException>в некоторых обстоятельствах.</xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="ed6a1-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="ed6a1-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-109">By default, this message is a warning.</span></span> <span data-ttu-id="ed6a1-110">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ed6a1-111">**Идентификатор ошибки:** BC42104</span><span class="sxs-lookup"><span data-stu-id="ed6a1-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed6a1-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ed6a1-112">To correct this error</span></span>  
  
-   <span data-ttu-id="ed6a1-113">Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается оператору, который считывает его.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="ed6a1-114">Один способ гарантировать, что переменная всегда имеет допустимое значение — инициализации как части объявления.</span><span class="sxs-lookup"><span data-stu-id="ed6a1-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="ed6a1-115">В разделе «Инициализация» в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ed6a1-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6a1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ed6a1-116">See Also</span></span>  
 <span data-ttu-id="ed6a1-117">[Оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ed6a1-117">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="ed6a1-118"> [Объявление переменных](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="ed6a1-118"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="ed6a1-119"> [Устранение неполадок, связанных с переменными](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span><span class="sxs-lookup"><span data-stu-id="ed6a1-119"> [Troubleshooting Variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span></span>
