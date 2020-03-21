---
title: Требования связывания
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: a0466eb5c24840c77a3b191f9b0e001f6b267fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181162"
---
# <a name="link-demands"></a><span data-ttu-id="9edb0-102">Требования связывания</span><span class="sxs-lookup"><span data-stu-id="9edb0-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="9edb0-103">Требование связывания вызывает проверку безопасности во время JIT-компиляции и выполняет проверку только непосредственно вызывающую сборку кода.</span><span class="sxs-lookup"><span data-stu-id="9edb0-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="9edb0-104">Связывание происходит, когда ваш код привязывается к ссылке на тип, включая ссылки на указатели функций и вызовы методов.</span><span class="sxs-lookup"><span data-stu-id="9edb0-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="9edb0-105">Если вызывающая сборка не имеет достаточных разрешений для связывания с кодом, связывание не разрешается, а при загрузке и запуске кода создается исключение времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="9edb0-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="9edb0-106">Требования связывания могут переопределяться в классах, наследующих от кода.</span><span class="sxs-lookup"><span data-stu-id="9edb0-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="9edb0-107">Обратите внимание, что полный обход стека не выполняется для этого типа требования, а код все равно подвержен атакам с заманиванием.</span><span class="sxs-lookup"><span data-stu-id="9edb0-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="9edb0-108">Например, если метод в сборке А защищен требованием ссылки, прямой абонент в сборке B оценивается на основе разрешений Собрания B.  Однако требование к ссылке не будет оценивать метод в сборке C, если он косвенно вызывает метод в сборке А с помощью метода в сборке B. Требование ссылки определяет только разрешения прямых абонентов в немедленной сборке вызовов должны быть связаны с вашим кодом.</span><span class="sxs-lookup"><span data-stu-id="9edb0-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="9edb0-109">Оно не определяет, какие разрешения должны иметь все вызывающие объекты для запуска кода.</span><span class="sxs-lookup"><span data-stu-id="9edb0-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="9edb0-110">Модификаторы обхода стека <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> и <xref:System.Security.CodeAccessPermission.PermitOnly%2A> не влияют на оценку требований связывания.</span><span class="sxs-lookup"><span data-stu-id="9edb0-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="9edb0-111">Поскольку требования связывания не выполняют обход стека, модификаторы обхода стека не оказывают влияния на требования связывания.</span><span class="sxs-lookup"><span data-stu-id="9edb0-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="9edb0-112">Если метод, защищенный спросом на ссылку, доступен через [Reflection,](../reflection-and-codedom/reflection.md)то требование ссылки проверяет непосредственного вызываемого кода, доступ к нему через отражение.</span><span class="sxs-lookup"><span data-stu-id="9edb0-112">If a method protected by a link demand is accessed through [Reflection](../reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="9edb0-113">Это справедливо как для обнаружения метода, так и для вызова метода, выполненного при помощи отражения.</span><span class="sxs-lookup"><span data-stu-id="9edb0-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="9edb0-114">Например, предположим, что <xref:System.Reflection.MethodInfo> код использует отражение для возвращения объекта, представляющего метод, защищенный требованием ссылки, а затем передает объект **MethodInfo** какой-либо другой код, который использует объект для ссылки на исходный метод.</span><span class="sxs-lookup"><span data-stu-id="9edb0-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="9edb0-115">В этом случае проверка спроса на ссылку происходит дважды: один раз для кода, который возвращает объект **MethodInfo,** и один раз для кода, который вызывает его.</span><span class="sxs-lookup"><span data-stu-id="9edb0-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9edb0-116">Требование связывания, выполняемое в статическом конструкторе класса, не защищает конструктор, так как статические конструкторы вызываются системой за пределами пути выполнения кода приложения.</span><span class="sxs-lookup"><span data-stu-id="9edb0-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="9edb0-117">В результате, когда требование связывания применяется ко всему классу, оно не может защитить доступ к статическому конструктору, хотя защищает остальную часть класса.</span><span class="sxs-lookup"><span data-stu-id="9edb0-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="9edb0-118">В следующем фрагменте кода декларативно указывается, что любой код, связываемый с методом `ReadData`, должен иметь разрешение `CustomPermission`.</span><span class="sxs-lookup"><span data-stu-id="9edb0-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="9edb0-119">Это гипотетическое разрешение, которого не существует в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9edb0-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="9edb0-120">Требование сделано путем передачи **SecurityAction.LinkDemand** флаг `CustomPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="9edb0-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9edb0-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9edb0-121">See also</span></span>

- [<span data-ttu-id="9edb0-122">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9edb0-122">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="9edb0-123">Безопасность доступа к коду</span><span class="sxs-lookup"><span data-stu-id="9edb0-123">Code Access Security</span></span>](code-access-security.md)
