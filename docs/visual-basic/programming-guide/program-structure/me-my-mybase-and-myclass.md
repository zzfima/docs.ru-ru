---
title: Me, My, MyBase и MyClass в Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- MyClass
- vb.Me
- MyBase
- vb.MyBase
- Me
- vb.MyClass
- vb.This
- vb.My
helpviewer_keywords:
- My object
- self-reference [Visual Basic], Me keyword
- MyClass keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], relationship to similar programming elements
- Me keyword [Visual Basic], referring to the current instance of an object
- Me keyword [Visual Basic]
- self-reference
- current instance [Visual Basic], Me keyword
- MyBase keyword [Visual Basic], relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4d06c97bdf4824e878d617b2d09993d18c60336b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="7bc56-102">Me, My, MyBase и MyClass в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7bc56-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="7bc56-103">`Me`, `My`, `MyBase`, и `MyClass` в Visual Basic имеют схожие имена, но для других целей.</span><span class="sxs-lookup"><span data-stu-id="7bc56-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="7bc56-104">В этом разделе описан каждый из этих сущностей, чтобы отличать их.</span><span class="sxs-lookup"><span data-stu-id="7bc56-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="7bc56-105">Me</span><span class="sxs-lookup"><span data-stu-id="7bc56-105">Me</span></span>  
 <span data-ttu-id="7bc56-106">`Me` Ключевое слово предоставляет способ ссылки на определенный экземпляр класса или структуры, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="7bc56-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="7bc56-107">`Me` ведет себя подобно объектной или структурной переменной, ссылающейся на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="7bc56-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="7bc56-108">С помощью `Me` особенно полезен для передачи данных о текущей выполняемой экземпляра класса или структуры в процедуру в другой класс, структура или модуль.</span><span class="sxs-lookup"><span data-stu-id="7bc56-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="7bc56-109">Например рассмотрим следующую процедуру в модуле.</span><span class="sxs-lookup"><span data-stu-id="7bc56-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="7bc56-110">Можно вызвать эту процедуру и передать текущий экземпляр <xref:System.Windows.Forms.Form> класса в качестве аргумента, используя следующую инструкцию.</span><span class="sxs-lookup"><span data-stu-id="7bc56-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="7bc56-111">My - функция</span><span class="sxs-lookup"><span data-stu-id="7bc56-111">My</span></span>  
 <span data-ttu-id="7bc56-112">`My` Обеспечивает простой и понятный доступ на ряд [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] классов, позволяя пользователям Visual Basic для взаимодействия с компьютера, приложения, параметры, ресурсы и т. д.</span><span class="sxs-lookup"><span data-stu-id="7bc56-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="7bc56-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="7bc56-113">MyBase</span></span>  
 <span data-ttu-id="7bc56-114">`MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="7bc56-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="7bc56-115">`MyBase` обычно используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе.</span><span class="sxs-lookup"><span data-stu-id="7bc56-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="7bc56-116">`MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="7bc56-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="7bc56-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="7bc56-117">MyClass</span></span>  
 <span data-ttu-id="7bc56-118">`MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован.</span><span class="sxs-lookup"><span data-stu-id="7bc56-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="7bc56-119">`MyClass` Аналогично `Me`, но все вызовы методов на нем рассматриваются, как если бы метод `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="7bc56-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bc56-120">См. также</span><span class="sxs-lookup"><span data-stu-id="7bc56-120">See Also</span></span>  
 [<span data-ttu-id="7bc56-121">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="7bc56-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
