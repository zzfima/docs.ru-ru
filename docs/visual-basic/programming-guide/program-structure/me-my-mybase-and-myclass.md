---
title: "Me, My, MyBase и MyClass в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
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
dev_langs:
- VB
helpviewer_keywords:
- My object
- self-reference, Me keyword
- MyClass keyword, relationship to similar programming elements
- Me keyword, relationship to similar programming elements
- Me keyword, referring to the current instance of an object
- Me keyword
- self-reference
- current instance, Me keyword
- MyBase keyword, relationship to similar programming elements
ms.assetid: f8e241ae-b1ed-4886-9aa0-08c632154029
caps.latest.revision: 15
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
ms.openlocfilehash: 3ba634eb28c25f47a0e88c856b916383b6ad15a2
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="dede0-102">Me, My, MyBase и MyClass в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dede0-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="dede0-103">`Me`, `My`, `MyBase`, и `MyClass` в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] имеют похожие имена, но для других целей.</span><span class="sxs-lookup"><span data-stu-id="dede0-103">`Me`, `My`, `MyBase`, and `MyClass` in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] have similar names, but different purposes.</span></span> <span data-ttu-id="dede0-104">В этом разделе описан каждый из этих сущностей, чтобы различать их.</span><span class="sxs-lookup"><span data-stu-id="dede0-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="dede0-105">Me</span><span class="sxs-lookup"><span data-stu-id="dede0-105">Me</span></span>  
 <span data-ttu-id="dede0-106">`Me` Ключевое слово предоставляет способ ссылки на определенный экземпляр класса или структуры, в котором в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="dede0-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="dede0-107">`Me`ведет себя подобно объектной или структурной переменной, ссылающейся на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="dede0-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="dede0-108">С помощью `Me` особенно полезно для передачи данных о текущей выполняемой экземпляра класса или структуры в процедуру в другой класс, структура или модуль.</span><span class="sxs-lookup"><span data-stu-id="dede0-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="dede0-109">Например предположим, что в модуле имеется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="dede0-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="dede0-110">Можно вызвать эту процедуру и передать текущий экземпляр <xref:System.Windows.Forms.Form>класса в качестве аргумента, используя следующую инструкцию.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="dede0-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="dede0-111">My - функция</span><span class="sxs-lookup"><span data-stu-id="dede0-111">My</span></span>  
 <span data-ttu-id="dede0-112">`My` Обеспечивает простой и понятный доступ на ряд [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] классов, включение [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] взаимодействие пользователя с компьютера, приложения, параметры, ресурсы и т. д.</span><span class="sxs-lookup"><span data-stu-id="dede0-112">The `My` feature provides easy and intuitive access to a number of [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] classes, enabling the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="dede0-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="dede0-113">MyBase</span></span>  
 <span data-ttu-id="dede0-114">`MyBase` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="dede0-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="dede0-115">`MyBase`обычно используется для доступа к членам базового класса, которые переопределены или скрыты в производном классе.</span><span class="sxs-lookup"><span data-stu-id="dede0-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="dede0-116">`MyBase.New`используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="dede0-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="dede0-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="dede0-117">MyClass</span></span>  
 <span data-ttu-id="dede0-118">`MyClass` Ключевое слово ведет себя подобно объектной переменной, ссылающейся на текущий экземпляр класса, который был изначально реализован.</span><span class="sxs-lookup"><span data-stu-id="dede0-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="dede0-119">`MyClass`Аналогично `Me`, но все вызовы методов рассматриваются, как если бы метод `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="dede0-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dede0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dede0-120">See Also</span></span>  
 [<span data-ttu-id="dede0-121">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="dede0-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
