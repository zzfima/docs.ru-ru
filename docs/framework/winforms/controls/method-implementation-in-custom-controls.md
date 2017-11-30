---
title: "Реализация методов в специализированных элементах управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user controls [Windows Forms], method implementation
- custom controls [Windows Forms], overloading methods
- custom controls [Windows Forms], method implementation
- methods [Windows Forms]
- methods [Windows Forms], custom controls
ms.assetid: 35d14fca-4bb4-4a27-8211-1f7a98ea27de
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c992197b653fb3999870247a3a4cdb4015612ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="method-implementation-in-custom-controls"></a><span data-ttu-id="c4410-102">Реализация методов в специализированных элементах управления</span><span class="sxs-lookup"><span data-stu-id="c4410-102">Method Implementation in Custom Controls</span></span>
<span data-ttu-id="c4410-103">Метод применяется в элементе управления точно так же, как и в любом другом компоненте.</span><span class="sxs-lookup"><span data-stu-id="c4410-103">A method is implemented in a control in the same manner a method would be implemented in any other component.</span></span>  
  
 <span data-ttu-id="c4410-104">В Visual Basic, если метод требуется для возврата значения, он выполняется как `Public Function`.</span><span class="sxs-lookup"><span data-stu-id="c4410-104">In Visual Basic, if a method is required to return a value, it is implemented as a `Public Function`.</span></span> <span data-ttu-id="c4410-105">Если значение не возвращается, метод выполняется как `Public Sub`.</span><span class="sxs-lookup"><span data-stu-id="c4410-105">If no value is returned, it is implemented as a `Public Sub`.</span></span> <span data-ttu-id="c4410-106">Методы объявляются согласно следующему синтаксису:</span><span class="sxs-lookup"><span data-stu-id="c4410-106">Methods are declared using the following syntax:</span></span>  
  
```vb  
Public Function ConvertMatterToEnergy(Matter as Integer) As Integer  
   ' Conversion code goes here.  
End Function  
```  
  
 <span data-ttu-id="c4410-107">Поскольку функции возвращают значения, в них необходимо указывать тип возвращаемого значения, например целое число, строка, объект и т. д.</span><span class="sxs-lookup"><span data-stu-id="c4410-107">Because functions return a value, they must specify a return type, such as integer, string, object, and so on.</span></span> <span data-ttu-id="c4410-108">Также необходимо задавать аргументы `Function` или процедуры `Sub` (если есть).</span><span class="sxs-lookup"><span data-stu-id="c4410-108">The arguments `Function` or `Sub` procedures take, if any, must also be specified.</span></span>  
  
 <span data-ttu-id="c4410-109">В C# нет различий между функциями и процедурами, а Visual Basic — есть.</span><span class="sxs-lookup"><span data-stu-id="c4410-109">C# makes no distinction between functions and procedures, as Visual Basic does.</span></span> <span data-ttu-id="c4410-110">Метод возвращает либо значение, либо ответ `void`.</span><span class="sxs-lookup"><span data-stu-id="c4410-110">A method either returns a value or returns `void`.</span></span> <span data-ttu-id="c4410-111">Синтаксис объявления открытого метода C# выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="c4410-111">The syntax for declaring a C# public method is:</span></span>  
  
```csharp  
public int ConvertMatterToEnergy(int matter)  
{  
   // Conversion code goes here.  
}  
```  
  
 <span data-ttu-id="c4410-112">При объявлении метода необходимо по возможности объявить все его аргументы и явные типы данных.</span><span class="sxs-lookup"><span data-stu-id="c4410-112">When you declare a method, declare all of its arguments as explicit data types whenever possible.</span></span> <span data-ttu-id="c4410-113">Аргументы с ссылками на объекты должны быть объявлены как особые типы классов, например `As Widget` вместо `As Object`.</span><span class="sxs-lookup"><span data-stu-id="c4410-113">Arguments that take object references should be declared as specific class types — for example, `As Widget` instead of `As Object`.</span></span> <span data-ttu-id="c4410-114">В Visual Basic настройка по умолчанию `Option Strict` применяет это правило автоматически.</span><span class="sxs-lookup"><span data-stu-id="c4410-114">In Visual Basic, the default setting `Option Strict` automatically enforces this rule.</span></span>  
  
 <span data-ttu-id="c4410-115">Аргументы с типами позволяют компилятору выявлять ошибки разработчиков перед запуском, а не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c4410-115">Typed arguments allow many developer errors to be caught by the compiler, rather than at run time.</span></span> <span data-ttu-id="c4410-116">Компилятор также отслеживает ошибки, а качество тестирования во время выполнения зависит от набора тестов.</span><span class="sxs-lookup"><span data-stu-id="c4410-116">The compiler always catches errors, whereas run-time testing is only as good as the test suite.</span></span>  
  
## <a name="overloaded-methods"></a><span data-ttu-id="c4410-117">Перегруженные методы</span><span class="sxs-lookup"><span data-stu-id="c4410-117">Overloaded Methods</span></span>  
 <span data-ttu-id="c4410-118">Если вы хотите разрешить пользователям элемента управления задавать для метода комбинации параметров, подготовьте несколько перегрузок метода с использованием явных типов данных.</span><span class="sxs-lookup"><span data-stu-id="c4410-118">If you want to allow users of your control to supply different combinations of parameters to a method, provide multiple overloads of the method, using explicit data types.</span></span> <span data-ttu-id="c4410-119">Не создавайте параметры, которые объявляются как `As Object` и могут содержать любые типы данных, — это может привести к ошибкам, которые не будут обнаружены во время тестирования.</span><span class="sxs-lookup"><span data-stu-id="c4410-119">Avoid creating parameters declared `As Object` that can contain any data type, as this can lead to errors that might not be caught in testing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4410-120">Универсальный тип данных в среде CLR — это `Object`, а не `Variant`.</span><span class="sxs-lookup"><span data-stu-id="c4410-120">The universal data type in the common language runtime is `Object` rather than `Variant`.</span></span> <span data-ttu-id="c4410-121">Тип `Variant` был исключен из языка.</span><span class="sxs-lookup"><span data-stu-id="c4410-121">`Variant` has been removed from the language.</span></span>  
  
 <span data-ttu-id="c4410-122">Например, метод `Spin` гипотетического элемента управления `Widget` позволяет либо прямо определить направление и скорость вращения, либо определить другой объект `Widget`, вращательный момент которого поглощается.</span><span class="sxs-lookup"><span data-stu-id="c4410-122">For example, the `Spin` method of a hypothetical `Widget` control might allow either direct specification of spin direction and speed, or specification of another `Widget` object from which angular momentum is to be absorbed:</span></span>  
  
```vb  
Overloads Public Sub Spin( _  
   ByVal SpinDirection As SpinDirectionsEnum, _  
   ByVal RevolutionsPerSecond As Double)  
   ' Implementation code here.  
End Sub  
Overloads Public Sub Spin(ByVal Driver As Widget) _  
   ' Implementation code here.  
End Sub  
```  
  
```csharp  
public void Spin(SpinDirectionsEnum spinDirection, double revolutionsPerSecond)  
{  
   // Implementation code here.  
}  
  
public void Spin(Widget driver)  
{  
   // Implementation code here.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4410-123">См. также</span><span class="sxs-lookup"><span data-stu-id="c4410-123">See Also</span></span>  
 [<span data-ttu-id="c4410-124">События</span><span class="sxs-lookup"><span data-stu-id="c4410-124">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="c4410-125">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4410-125">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)
