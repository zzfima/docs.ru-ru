---
title: Доступ к свойству по умолчанию определяется неоднозначно между наследуемые члены интерфейса &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 65a10067284cad3bf56ecdc441ebefa0a740ef53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590859"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a><span data-ttu-id="3d192-102">Доступ к свойству по умолчанию определяется неоднозначно между наследуемые члены интерфейса &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса1&gt; &#39; и &#39; &lt;defaultpropertyname&gt; &#39; интерфейса &#39; &lt;имя_интерфейса2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="3d192-102">Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;</span></span>
<span data-ttu-id="3d192-103">Интерфейс наследует от двух интерфейсов, каждый из которых объявляет свойство по умолчанию с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="3d192-103">An interface inherits from two interfaces, each of which declares a default property with the same name.</span></span> <span data-ttu-id="3d192-104">Компилятор не может разрешить доступ к этому свойству по умолчанию без уточнения.</span><span class="sxs-lookup"><span data-stu-id="3d192-104">The compiler cannot resolve an access to this default property without qualification.</span></span> <span data-ttu-id="3d192-105">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d192-105">The following example illustrates this.</span></span>  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="3d192-106">При указании `testObj(1)`, компилятор пытается разрешить ее свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3d192-106">When you specify `testObj(1)`, the compiler tries to resolve it to the default property.</span></span> <span data-ttu-id="3d192-107">Однако существуют два свойства по умолчанию невозможно из-за наследуемых интерфейсов, поэтому компилятор создает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="3d192-107">However, there are two possible default properties because of the inherited interfaces, so the compiler signals this error.</span></span>  
  
 <span data-ttu-id="3d192-108">**Идентификатор ошибки:** BC30686</span><span class="sxs-lookup"><span data-stu-id="3d192-108">**Error ID:** BC30686</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3d192-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="3d192-109">To correct this error</span></span>  
  
-   <span data-ttu-id="3d192-110">Избегайте наследования элементов с тем же именем.</span><span class="sxs-lookup"><span data-stu-id="3d192-110">Avoid inheriting any members with the same name.</span></span> <span data-ttu-id="3d192-111">В предыдущем примере если `testObj` не требуется ни один из членов, например, `Iface2`, объявите его следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d192-111">In the preceding example, if `testObj` does not need any of the members of, say, `Iface2`, then declare it as follows:</span></span>  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     <span data-ttu-id="3d192-112">- или -</span><span class="sxs-lookup"><span data-stu-id="3d192-112">-or-</span></span>  
  
-   <span data-ttu-id="3d192-113">Реализуйте наследуемый интерфейс в классе.</span><span class="sxs-lookup"><span data-stu-id="3d192-113">Implement the inheriting interface in a class.</span></span> <span data-ttu-id="3d192-114">Затем можно реализовать все наследуемые свойства с различными именами.</span><span class="sxs-lookup"><span data-stu-id="3d192-114">Then you can implement each of the inherited properties with different names.</span></span> <span data-ttu-id="3d192-115">Однако только один из них может быть свойство по умолчанию для реализующего класса.</span><span class="sxs-lookup"><span data-stu-id="3d192-115">However, only one of them can be the default property of the implementing class.</span></span> <span data-ttu-id="3d192-116">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="3d192-116">The following example illustrates this.</span></span>  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3d192-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3d192-117">See Also</span></span>  
 [<span data-ttu-id="3d192-118">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="3d192-118">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
