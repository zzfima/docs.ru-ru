---
title: Me, My, MyBase и MyClass
ms.date: 07/20/2015
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
ms.openlocfilehash: a21dfeb12e8d99f5f8b8afede084846711c299ab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401433"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="f5215-102">Me, My, MyBase и MyClass в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5215-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="f5215-103">`Me`, `My` `MyBase`, `MyClass` , и в Visual Basic имеют похожие названия, но разные цели.</span><span class="sxs-lookup"><span data-stu-id="f5215-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="f5215-104">Эта тема описывает каждый из этих сущностей для того, чтобы различать их.</span><span class="sxs-lookup"><span data-stu-id="f5215-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="f5215-105">У меня</span><span class="sxs-lookup"><span data-stu-id="f5215-105">Me</span></span>  
 <span data-ttu-id="f5215-106">Ключевое `Me` слово предоставляет способ отсылки к конкретному экземпляру класса или структуры, в котором код в настоящее время исполняется.</span><span class="sxs-lookup"><span data-stu-id="f5215-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="f5215-107">`Me`ведет себя как переменная объекта или переменная структуры, относящаяся к текущему экземпляру.</span><span class="sxs-lookup"><span data-stu-id="f5215-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="f5215-108">Использование `Me` особенно полезно для передачи информации о данном экземпляре выполнения класса или структуры процедуре в другом классе, структуре или модуле.</span><span class="sxs-lookup"><span data-stu-id="f5215-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="f5215-109">Например, предположим, что в модуле есть следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="f5215-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="f5215-110">Вы можете вызвать эту процедуру <xref:System.Windows.Forms.Form> и передать текущий экземпляр класса в качестве аргумента, используя следующее утверждение.</span><span class="sxs-lookup"><span data-stu-id="f5215-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="f5215-111">My</span><span class="sxs-lookup"><span data-stu-id="f5215-111">My</span></span>  
 <span data-ttu-id="f5215-112">Функция `My` обеспечивает простой и интуитивно понятный доступ к ряду классов .NET Framework, позволяя пользователю Visual Basic взаимодействовать с компьютером, приложением, настройками, ресурсами и так далее.</span><span class="sxs-lookup"><span data-stu-id="f5215-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="f5215-113">MyBase</span><span class="sxs-lookup"><span data-stu-id="f5215-113">MyBase</span></span>  
 <span data-ttu-id="f5215-114">Ключевое `MyBase` слово ведет себя как объектная переменная, относящаяся к базовому классу текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="f5215-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="f5215-115">`MyBase`обычно используется для доступа к членам базового класса, которые переопределены или затенены в производных классах.</span><span class="sxs-lookup"><span data-stu-id="f5215-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="f5215-116">`MyBase.New`используется для явного вызова конструктора базового класса из производного конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="f5215-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="f5215-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="f5215-117">MyClass</span></span>  
 <span data-ttu-id="f5215-118">Ключевое `MyClass` слово ведет себя как объектная переменная, относящаяся к текущему экземпляру класса в первоначальнореализованном виде.</span><span class="sxs-lookup"><span data-stu-id="f5215-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="f5215-119">`MyClass`похож на `Me`, но все методы звонки на `NotOverridable`него рассматриваются как если бы метод был .</span><span class="sxs-lookup"><span data-stu-id="f5215-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5215-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f5215-120">See also</span></span>

- [<span data-ttu-id="f5215-121">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="f5215-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
