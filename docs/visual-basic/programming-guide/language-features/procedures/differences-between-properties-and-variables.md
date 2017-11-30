---
title: "Различия между свойствами и переменными в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cb30972e2b49a7005749f57c0223b9fa493cde52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="56174-102">Различия между свойствами и переменными в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56174-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="56174-103">Переменные и свойства представляют значения, которые можно открыть.</span><span class="sxs-lookup"><span data-stu-id="56174-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="56174-104">Однако существуют различия в хранении и реализации.</span><span class="sxs-lookup"><span data-stu-id="56174-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="56174-105">Переменные</span><span class="sxs-lookup"><span data-stu-id="56174-105">Variables</span></span>  
 <span data-ttu-id="56174-106">Объект *переменной* соответствующее расположение в памяти.</span><span class="sxs-lookup"><span data-stu-id="56174-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="56174-107">Можно определить переменную с одиночной инструкции объявления.</span><span class="sxs-lookup"><span data-stu-id="56174-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="56174-108">Переменная может быть *локальной переменной*, определенные внутри процедуры и доступна только в рамках этой процедуры, или может быть *переменной-члена*, определена в модуля, класса или структуры, но не внутри любого процедура.</span><span class="sxs-lookup"><span data-stu-id="56174-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="56174-109">Переменная члена также называется *поля*.</span><span class="sxs-lookup"><span data-stu-id="56174-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="56174-110">Свойства</span><span class="sxs-lookup"><span data-stu-id="56174-110">Properties</span></span>  
 <span data-ttu-id="56174-111">Объект *свойство* является элементом данных, определяемым для модуля, класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="56174-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="56174-112">Вы определили свойство с помощью блока кода между `Property` и `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="56174-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="56174-113">Блок кода содержит `Get` процедуре `Set` или обе.</span><span class="sxs-lookup"><span data-stu-id="56174-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="56174-114">Эти процедуры называются *процедуры свойств* или *свойствам*.</span><span class="sxs-lookup"><span data-stu-id="56174-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="56174-115">Помимо извлечения или сохранения значения свойства, они могут выполнять пользовательские действия, такие как обновление счетчика доступа.</span><span class="sxs-lookup"><span data-stu-id="56174-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="56174-116">Различия</span><span class="sxs-lookup"><span data-stu-id="56174-116">Differences</span></span>  
 <span data-ttu-id="56174-117">Ниже приведены некоторые важные отличия, переменные и свойства.</span><span class="sxs-lookup"><span data-stu-id="56174-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="56174-118">Рассматриваемый</span><span class="sxs-lookup"><span data-stu-id="56174-118">Point of difference</span></span>|<span data-ttu-id="56174-119">Переменная</span><span class="sxs-lookup"><span data-stu-id="56174-119">Variable</span></span>|<span data-ttu-id="56174-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="56174-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="56174-121">Объявление</span><span class="sxs-lookup"><span data-stu-id="56174-121">Declaration</span></span>|<span data-ttu-id="56174-122">Одиночный оператор объявления</span><span class="sxs-lookup"><span data-stu-id="56174-122">Single declaration statement</span></span>|<span data-ttu-id="56174-123">Последовательность инструкций в блоке кода</span><span class="sxs-lookup"><span data-stu-id="56174-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="56174-124">Реализация</span><span class="sxs-lookup"><span data-stu-id="56174-124">Implementation</span></span>|<span data-ttu-id="56174-125">Одно место хранения</span><span class="sxs-lookup"><span data-stu-id="56174-125">Single storage location</span></span>|<span data-ttu-id="56174-126">Исполняемый код (процедуры свойства)</span><span class="sxs-lookup"><span data-stu-id="56174-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="56174-127">Хранилище</span><span class="sxs-lookup"><span data-stu-id="56174-127">Storage</span></span>|<span data-ttu-id="56174-128">Непосредственно связан с переменной</span><span class="sxs-lookup"><span data-stu-id="56174-128">Directly associated with variable's value</span></span>|<span data-ttu-id="56174-129">Обычно имеет внутреннее хранилище недоступно вне свойства содержащего класса или модуля</span><span class="sxs-lookup"><span data-stu-id="56174-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="56174-130">Значение свойства может существовать или не существовать в виде хранимого элемента <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="56174-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="56174-131">Исполняемый код</span><span class="sxs-lookup"><span data-stu-id="56174-131">Executable code</span></span>|<span data-ttu-id="56174-132">Нет</span><span class="sxs-lookup"><span data-stu-id="56174-132">None</span></span>|<span data-ttu-id="56174-133">Необходимо иметь по крайней мере одну процедуру</span><span class="sxs-lookup"><span data-stu-id="56174-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="56174-134">Чтение и запись</span><span class="sxs-lookup"><span data-stu-id="56174-134">Read and write access</span></span>|<span data-ttu-id="56174-135">Чтение и запись или только для чтения</span><span class="sxs-lookup"><span data-stu-id="56174-135">Read/write or read-only</span></span>|<span data-ttu-id="56174-136">Для чтения и записи только для чтения или только для записи</span><span class="sxs-lookup"><span data-stu-id="56174-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="56174-137">Настраиваемые действия (в дополнение к принятию или возвращению значения)</span><span class="sxs-lookup"><span data-stu-id="56174-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="56174-138">Не удается</span><span class="sxs-lookup"><span data-stu-id="56174-138">Not possible</span></span>|<span data-ttu-id="56174-139">Может выполняться как часть задания или получения значения свойства</span><span class="sxs-lookup"><span data-stu-id="56174-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="56174-140"><sup>1</sup> в отличие от переменной, значение свойства может не соответствовать непосредственно к одному элементу хранилища.</span><span class="sxs-lookup"><span data-stu-id="56174-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="56174-141">Хранилище может быть разбито на части для удобства или безопасности, или значение может храниться в зашифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="56174-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="56174-142">В таких случаях `Get` процедуры будет собирать фрагменты или расшифровать хранимое значение и `Set` процедуры будет шифровать новое значение или разбейте его на составные части хранилища.</span><span class="sxs-lookup"><span data-stu-id="56174-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="56174-143">Значение свойства может быть временным, например, время дня, в этом случае `Get` процедура будет вычислять его на лету при каждом доступе к свойству.</span><span class="sxs-lookup"><span data-stu-id="56174-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56174-144">См. также</span><span class="sxs-lookup"><span data-stu-id="56174-144">See Also</span></span>  
 [<span data-ttu-id="56174-145">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="56174-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="56174-146">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="56174-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="56174-147">Оператор Property</span><span class="sxs-lookup"><span data-stu-id="56174-147">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="56174-148">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="56174-148">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="56174-149">Практическое руководство. Создание свойства</span><span class="sxs-lookup"><span data-stu-id="56174-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="56174-150">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="56174-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="56174-151">Практическое руководство. Вызов процедуры свойства</span><span class="sxs-lookup"><span data-stu-id="56174-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="56174-152">Как: объявление и вызов свойства по умолчанию в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="56174-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="56174-153">Практическое руководство. Запись значения в свойство</span><span class="sxs-lookup"><span data-stu-id="56174-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="56174-154">Практическое руководство. Получение значения из свойства</span><span class="sxs-lookup"><span data-stu-id="56174-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
