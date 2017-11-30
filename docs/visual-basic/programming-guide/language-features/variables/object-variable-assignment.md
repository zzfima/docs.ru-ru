---
title: "Присваивание объектных переменных (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb6b53bebddc1c9cf1b9088e96ded36a5e1c5242
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="efce0-102">Присваивание объектных переменных (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="efce0-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="efce0-103">Используйте обычный оператор присваивания для назначения объекта переменной объекта.</span><span class="sxs-lookup"><span data-stu-id="efce0-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="efce0-104">Можно присвоить выражение объекта или [ничего](../../../../visual-basic/language-reference/nothing.md) ключевое слово, как приведенный ниже пример иллюстрирует.</span><span class="sxs-lookup"><span data-stu-id="efce0-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="efce0-105">`Nothing`означает нет объекта, в настоящее время назначен переменной.</span><span class="sxs-lookup"><span data-stu-id="efce0-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="efce0-106">Инициализация</span><span class="sxs-lookup"><span data-stu-id="efce0-106">Initialization</span></span>  
 <span data-ttu-id="efce0-107">При запуске кода, переменные инициализируются объекта `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="efce0-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="efce0-108">Тех, чьи объявления содержат инициализацию инициализируются значениями, задаваемый при выполнении инструкций объявления.</span><span class="sxs-lookup"><span data-stu-id="efce0-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="efce0-109">Можно включить инициализацию в объявление с помощью [New](../../../../visual-basic/language-reference/operators/new-operator.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="efce0-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="efce0-110">Приведенные ниже операторы объявления объявляют переменные объекта `testUri` и `ver` и присвоить им определенные объекты.</span><span class="sxs-lookup"><span data-stu-id="efce0-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="efce0-111">Каждый использует один из перегруженных конструкторов соответствующего класса для инициализации объекта.</span><span class="sxs-lookup"><span data-stu-id="efce0-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="efce0-112">Отключение</span><span class="sxs-lookup"><span data-stu-id="efce0-112">Disassociation</span></span>  
 <span data-ttu-id="efce0-113">Задание для переменной объекта `Nothing` разрывает связь переменной с конкретным объектом.</span><span class="sxs-lookup"><span data-stu-id="efce0-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="efce0-114">Это предотвращает случайное изменение объекта при изменении переменной.</span><span class="sxs-lookup"><span data-stu-id="efce0-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="efce0-115">Он также позволяет проверить, является ли переменная ссылку на допустимый объект, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="efce0-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="efce0-116">Если объект, на который ссылается переменная находится в другом приложении, этот тест не может определить, имеет ли приложение завершается или просто недействительными объекта.</span><span class="sxs-lookup"><span data-stu-id="efce0-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="efce0-117">Объектной переменной со значением `Nothing` также называется *ссылка null*.</span><span class="sxs-lookup"><span data-stu-id="efce0-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="efce0-118">Текущий экземпляр</span><span class="sxs-lookup"><span data-stu-id="efce0-118">Current Instance</span></span>  
 <span data-ttu-id="efce0-119">*Текущего экземпляра* объекта является то, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="efce0-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="efce0-120">Поскольку весь код выполняется внутри процедуры, текущий экземпляр является тот, в которой была вызвана процедура.</span><span class="sxs-lookup"><span data-stu-id="efce0-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="efce0-121">`Me` Ключевое слово выступает в качестве объектной переменной, ссылающейся на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="efce0-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="efce0-122">Если процедура не является [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), он может использовать `Me` ключевое слово для получения указателя на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="efce0-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="efce0-123">Общие процедуры не может быть связан с определенным экземпляром класса.</span><span class="sxs-lookup"><span data-stu-id="efce0-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="efce0-124">С помощью `Me` особенно полезен для передачи текущего экземпляра процедуре другого модуля.</span><span class="sxs-lookup"><span data-stu-id="efce0-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="efce0-125">Предположим, например, число XML-документов и хотите добавить стандартный текст ко всем из них.</span><span class="sxs-lookup"><span data-stu-id="efce0-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="efce0-126">В следующем примере определяется процедура для этого.</span><span class="sxs-lookup"><span data-stu-id="efce0-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="efce0-127">Каждый объект XML-документа может затем вызвать процедуру и передать ее текущий экземпляр в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="efce0-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="efce0-128">В следующем примере это показано.</span><span class="sxs-lookup"><span data-stu-id="efce0-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="efce0-129">См. также</span><span class="sxs-lookup"><span data-stu-id="efce0-129">See Also</span></span>  
 [<span data-ttu-id="efce0-130">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="efce0-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="efce0-131">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="efce0-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="efce0-132">Значения объектных переменных</span><span class="sxs-lookup"><span data-stu-id="efce0-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="efce0-133">Как: объявление объектной переменной и присвоение ей объекта в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="efce0-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="efce0-134">Практическое руководство. Как сделать так, чтобы объектная переменная не указывала ни на какой экземпляр</span><span class="sxs-lookup"><span data-stu-id="efce0-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="efce0-135">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="efce0-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
