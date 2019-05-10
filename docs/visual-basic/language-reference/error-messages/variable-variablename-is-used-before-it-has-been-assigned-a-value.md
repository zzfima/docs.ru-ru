---
title: Переменная <variablename> используется до того, как ей присвоено значение
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: a2ba752b95933d146da090a58c416015db75e106
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662674"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="dca6a-102">Переменной "\<имя_переменной >" используется, прежде чем ей было назначено значение</span><span class="sxs-lookup"><span data-stu-id="dca6a-102">Variable '\<variablename>' is used before it has been assigned a value</span></span>
<span data-ttu-id="dca6a-103">Переменной "\<имя_переменной >" используется, прежде чем ей было назначено значение.</span><span class="sxs-lookup"><span data-stu-id="dca6a-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="dca6a-104">Во время выполнения может возникнуть исключение "пустая ссылка".</span><span class="sxs-lookup"><span data-stu-id="dca6a-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="dca6a-105">Приложение имеет по крайней мере один возможный путь во всем коде, который считывает значение переменной, прежде чем к нему было назначено значение.</span><span class="sxs-lookup"><span data-stu-id="dca6a-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="dca6a-106">Если переменной никогда не назначалось значение, она содержит значение по умолчанию для своего типа данных.</span><span class="sxs-lookup"><span data-stu-id="dca6a-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="dca6a-107">Для ссылочного типа данных значение по умолчанию — [Nothing](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="dca6a-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="dca6a-108">Чтение переменной ссылки, которая имеет значение `Nothing` , в некоторых случаях может привести к исключению <xref:System.NullReferenceException> .</span><span class="sxs-lookup"><span data-stu-id="dca6a-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="dca6a-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="dca6a-109">By default, this message is a warning.</span></span> <span data-ttu-id="dca6a-110">Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dca6a-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="dca6a-111">**Идентификатор ошибки:** BC42104</span><span class="sxs-lookup"><span data-stu-id="dca6a-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dca6a-112">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="dca6a-112">To correct this error</span></span>  
  
- <span data-ttu-id="dca6a-113">Проверьте логику потока управления и убедитесь, что переменная имеет допустимое значение, прежде чем управление передается оператору, который считывает его.</span><span class="sxs-lookup"><span data-stu-id="dca6a-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
- <span data-ttu-id="dca6a-114">Для инициализации его как часть объявления является один из способов, чтобы гарантировать, что переменная всегда имеет допустимое значение.</span><span class="sxs-lookup"><span data-stu-id="dca6a-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="dca6a-115">См. в разделе «Инициализация» в [оператор Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dca6a-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca6a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dca6a-116">See also</span></span>

- [<span data-ttu-id="dca6a-117">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="dca6a-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="dca6a-118">Объявление переменных</span><span class="sxs-lookup"><span data-stu-id="dca6a-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="dca6a-119">Устранение неполадок, связанных с переменными</span><span class="sxs-lookup"><span data-stu-id="dca6a-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
