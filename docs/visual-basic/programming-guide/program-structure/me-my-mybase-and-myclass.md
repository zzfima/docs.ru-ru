---
title: Me, My, MyBase и MyClass в Visual Basic
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
ms.openlocfilehash: 7df146e09a1d7cd730f4cf539d6823f7ced44bd1
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002531"
---
# <a name="me-my-mybase-and-myclass-in-visual-basic"></a><span data-ttu-id="13bac-102">Me, My, MyBase и MyClass в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="13bac-102">Me, My, MyBase, and MyClass in Visual Basic</span></span>
<span data-ttu-id="13bac-103">`Me`, `My`, `MyBase` и `MyClass` в Visual Basic имеют похожие имена, но разные цели.</span><span class="sxs-lookup"><span data-stu-id="13bac-103">`Me`, `My`, `MyBase`, and `MyClass` in Visual Basic have similar names, but different purposes.</span></span> <span data-ttu-id="13bac-104">В этом разделе описывается каждая из этих сущностей, чтобы их можно было отличать.</span><span class="sxs-lookup"><span data-stu-id="13bac-104">This topic describes each of these entities in order to distinguish them.</span></span>  
  
## <a name="me"></a><span data-ttu-id="13bac-105">Me</span><span class="sxs-lookup"><span data-stu-id="13bac-105">Me</span></span>  
 <span data-ttu-id="13bac-106">Ключевое слово `Me` позволяет ссылаться на конкретный экземпляр класса или структуры, в которой в данный момент выполняется код.</span><span class="sxs-lookup"><span data-stu-id="13bac-106">The `Me` keyword provides a way to refer to the specific instance of a class or structure in which the code is currently executing.</span></span> <span data-ttu-id="13bac-107">`Me` ведет себя как либо переменная объекта, либо переменная структуры, ссылающаяся на текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="13bac-107">`Me` behaves like either an object variable or a structure variable referring to the current instance.</span></span> <span data-ttu-id="13bac-108">Использование `Me` особенно полезно для передачи сведений о текущем выполняющемся экземпляре класса или структуры в процедуру в другом классе, структуре или модуле.</span><span class="sxs-lookup"><span data-stu-id="13bac-108">Using `Me` is particularly useful for passing information about the currently executing instance of a class or structure to a procedure in another class, structure, or module.</span></span>  
  
 <span data-ttu-id="13bac-109">Например, предположим, что в модуле имеется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="13bac-109">For example, suppose you have the following procedure in a module.</span></span>  
  
```vb  
Sub ChangeFormColor(FormName As Form)  
   Randomize()  
   FormName.BackColor = Color.FromArgb(Rnd() * 256, Rnd() * 256, Rnd() * 256)  
End Sub  
```  
  
 <span data-ttu-id="13bac-110">Эту процедуру можно вызвать и передать текущий экземпляр класса <xref:System.Windows.Forms.Form> в качестве аргумента с помощью следующей инструкции.</span><span class="sxs-lookup"><span data-stu-id="13bac-110">You can call this procedure and pass the current instance of the <xref:System.Windows.Forms.Form> class as an argument by using the following statement.</span></span>  
  
```vb  
ChangeFormColor(Me)  
```  
  
## <a name="my"></a><span data-ttu-id="13bac-111">My - функция</span><span class="sxs-lookup"><span data-stu-id="13bac-111">My</span></span>  
 <span data-ttu-id="13bac-112">Функция `My` обеспечивает простой и интуитивно понятный доступ к ряду .NET Framework классов, позволяя Visual Basic пользователю взаимодействовать с компьютером, приложением, параметрами, ресурсами и т. д.</span><span class="sxs-lookup"><span data-stu-id="13bac-112">The `My` feature provides easy and intuitive access to a number of .NET Framework classes, enabling the Visual Basic user to interact with the computer, application, settings, resources, and so on.</span></span>  
  
## <a name="mybase"></a><span data-ttu-id="13bac-113">Слово</span><span class="sxs-lookup"><span data-stu-id="13bac-113">MyBase</span></span>  
 <span data-ttu-id="13bac-114">Ключевое слово `MyBase` ведет себя как объектная переменная, ссылающаяся на базовый класс текущего экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="13bac-114">The `MyBase` keyword behaves like an object variable referring to the base class of the current instance of a class.</span></span> <span data-ttu-id="13bac-115">`MyBase` обычно используется для доступа к членам базового класса, которые переопределяются или переобъявляются в производном классе.</span><span class="sxs-lookup"><span data-stu-id="13bac-115">`MyBase` is commonly used to access base class members that are overridden or shadowed in a derived class.</span></span> <span data-ttu-id="13bac-116">`MyBase.New` используется для явного вызова конструктора базового класса из конструктора производного класса.</span><span class="sxs-lookup"><span data-stu-id="13bac-116">`MyBase.New` is used to explicitly call a base class constructor from a derived class constructor.</span></span>  
  
## <a name="myclass"></a><span data-ttu-id="13bac-117">MyClass</span><span class="sxs-lookup"><span data-stu-id="13bac-117">MyClass</span></span>  
 <span data-ttu-id="13bac-118">Ключевое слово `MyClass` ведет себя как объектная переменная, ссылающаяся на текущий экземпляр класса как изначально реализованный.</span><span class="sxs-lookup"><span data-stu-id="13bac-118">The `MyClass` keyword behaves like an object variable referring to the current instance of a class as originally implemented.</span></span> <span data-ttu-id="13bac-119">`MyClass` аналогична `Me`, но все вызовы методов в нем обрабатываются так, как если бы метод был `NotOverridable`.</span><span class="sxs-lookup"><span data-stu-id="13bac-119">`MyClass` is similar to `Me`, but all method calls on it are treated as if the method were `NotOverridable`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13bac-120">См. также</span><span class="sxs-lookup"><span data-stu-id="13bac-120">See also</span></span>

- [<span data-ttu-id="13bac-121">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="13bac-121">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
