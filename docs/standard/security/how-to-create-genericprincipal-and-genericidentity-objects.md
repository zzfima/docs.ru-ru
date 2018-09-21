---
title: Практическое руководство. Создание объектов GenericPrincipal и GenericIdentity
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Creating Generic Identity Objects
- GenericPrincipal Objects
- Creating GenericPrincipal Objects
- GenericIdentity Objects
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79b5e05fe9133eb2282eedefa001e64ece5e0f57
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532156"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a><span data-ttu-id="48e25-102">Практическое руководство. Создание объектов GenericPrincipal и GenericIdentity</span><span class="sxs-lookup"><span data-stu-id="48e25-102">How to: Create GenericPrincipal and GenericIdentity Objects</span></span>
<span data-ttu-id="48e25-103">Можно использовать <xref:System.Security.Principal.GenericIdentity> класс в сочетании с <xref:System.Security.Principal.GenericPrincipal> класса для создания схемы авторизации, которая существует независимо от домена Windows.</span><span class="sxs-lookup"><span data-stu-id="48e25-103">You can use the <xref:System.Security.Principal.GenericIdentity> class in conjunction with the <xref:System.Security.Principal.GenericPrincipal> class to create an authorization scheme that exists independent of a Windows domain.</span></span>  
  
### <a name="to-create-a-genericprincipal-object"></a><span data-ttu-id="48e25-104">Создание объекта GenericPrincipal</span><span class="sxs-lookup"><span data-stu-id="48e25-104">To create a GenericPrincipal object</span></span>  
  
1.  <span data-ttu-id="48e25-105">Создайте новый экземпляр класса identity и инициализируйте его с необходимым именем.</span><span class="sxs-lookup"><span data-stu-id="48e25-105">Create a new instance of the identity class and initialize it with the name you want it to hold.</span></span> <span data-ttu-id="48e25-106">Следующий код создает новый объект **GenericIdentity** и инициализирует его с именем `MyUser`.</span><span class="sxs-lookup"><span data-stu-id="48e25-106">The following code creates a new **GenericIdentity** object and initializes it with the name `MyUser`.</span></span>  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  <span data-ttu-id="48e25-107">Создайте новый экземпляр класса **GenericPrincipal** и инициализируйте его с ранее созданным объектом **GenericIdentity** и массивом строк, представляющими роли, которые требуется связать с этим участником.</span><span class="sxs-lookup"><span data-stu-id="48e25-107">Create a new instance of the **GenericPrincipal** class and initialize it with the previously created **GenericIdentity** object and an array of strings that represent the roles that you want associated with this principal.</span></span> <span data-ttu-id="48e25-108">В следующем примере кода задается массив строк, представляющих роль администратора и роль пользователя.</span><span class="sxs-lookup"><span data-stu-id="48e25-108">The following code example specifies an array of strings that represent an administrator role and a user role.</span></span> <span data-ttu-id="48e25-109">Затем **GenericPrincipal** инициализируется с предыдущим **GenericIdentity** и массивом строк.</span><span class="sxs-lookup"><span data-stu-id="48e25-109">The **GenericPrincipal** is then initialized with the previous **GenericIdentity** and the string array.</span></span>  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  <span data-ttu-id="48e25-110">Для подключения участника к текущему потоку используйте следующий код.</span><span class="sxs-lookup"><span data-stu-id="48e25-110">Use the following code to attach the principal to the current thread.</span></span> <span data-ttu-id="48e25-111">Это полезно в ситуациях, когда участника следует проверить несколько раз, он должен быть проверен кодом, выполняющимся в приложении, или он должен быть проверен <xref:System.Security.Permissions.PrincipalPermission> объекта.</span><span class="sxs-lookup"><span data-stu-id="48e25-111">This is valuable in situations where the principal must be validated several times, it must be validated by other code running in your application, or it must be validated by a <xref:System.Security.Permissions.PrincipalPermission> object.</span></span> <span data-ttu-id="48e25-112">Объект Principal по-прежнему можно проверять на основании ролей без подключения его к потоку.</span><span class="sxs-lookup"><span data-stu-id="48e25-112">You can still perform role-based validation on the principal object without attaching it to the thread.</span></span> <span data-ttu-id="48e25-113">Дополнительные сведения см. в разделе [Замена объекта Principal](../../../docs/standard/security/replacing-a-principal-object.md).</span><span class="sxs-lookup"><span data-stu-id="48e25-113">For more information, see [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md).</span></span>  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## <a name="example"></a><span data-ttu-id="48e25-114">Пример</span><span class="sxs-lookup"><span data-stu-id="48e25-114">Example</span></span>  
 <span data-ttu-id="48e25-115">В следующем примере кода показано, как создать экземпляр объекта **GenericPrincipal** и **GenericIdentity**.</span><span class="sxs-lookup"><span data-stu-id="48e25-115">The following code example demonstrates how to create an instance of a **GenericPrincipal** and a **GenericIdentity**.</span></span> <span data-ttu-id="48e25-116">Данный код выводит значения этих объектов на консоль.</span><span class="sxs-lookup"><span data-stu-id="48e25-116">This code displays the values of these objects to the console.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Principal  
Imports System.Threading  
  
Public Class Class1  
  
    Public Shared Sub Main()  
        ' Create generic identity.  
        Dim MyIdentity As New GenericIdentity("MyIdentity")  
  
        ' Create generic principal.  
        Dim MyStringArray As String() =  {"Manager", "Teller"}  
        Dim MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
  
        ' Attach the principal to the current thread.  
        ' This is not required unless repeated validation must occur,  
        ' other code in your application must validate, or the   
        ' PrincipalPermisson object is used.   
        Thread.CurrentPrincipal = MyPrincipal  
  
        ' Print values to the console.  
        Dim Name As String = MyPrincipal.Identity.Name  
        Dim Auth As Boolean = MyPrincipal.Identity.IsAuthenticated  
        Dim IsInRole As Boolean = MyPrincipal.IsInRole("Manager")  
  
        Console.WriteLine("The Name is: {0}", Name)  
        Console.WriteLine("The IsAuthenticated is: {0}", Auth)  
        Console.WriteLine("Is this a Manager? {0}", IsInRole)  
  
    End Sub  
  
End Class  
```  
  
```csharp  
using System;  
using System.Security.Principal;  
using System.Threading;  
  
public class Class1  
{  
    public static int Main(string[] args)  
    {  
    // Create generic identity.  
    GenericIdentity MyIdentity = new GenericIdentity("MyIdentity");  
  
    // Create generic principal.  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal =   
        new GenericPrincipal(MyIdentity, MyStringArray);  
  
    // Attach the principal to the current thread.  
    // This is not required unless repeated validation must occur,  
    // other code in your application must validate, or the   
    // PrincipalPermisson object is used.   
    Thread.CurrentPrincipal = MyPrincipal;  
  
    // Print values to the console.  
    String Name =  MyPrincipal.Identity.Name;  
    bool Auth =  MyPrincipal.Identity.IsAuthenticated;   
    bool IsInRole =  MyPrincipal.IsInRole("Manager");  
  
    Console.WriteLine("The Name is: {0}", Name);  
    Console.WriteLine("The IsAuthenticated is: {0}", Auth);  
    Console.WriteLine("Is this a Manager? {0}", IsInRole);  
  
    return 0;  
    }  
}  
```  
  
 <span data-ttu-id="48e25-117">Во время выполнения приложение выводит примерно следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="48e25-117">When executed, the application displays output similar to the following.</span></span>  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## <a name="see-also"></a><span data-ttu-id="48e25-118">См. также</span><span class="sxs-lookup"><span data-stu-id="48e25-118">See also</span></span>

- <xref:System.Security.Principal.GenericIdentity>  
- <xref:System.Security.Principal.GenericPrincipal>  
- <xref:System.Security.Permissions.PrincipalPermission>  
- [<span data-ttu-id="48e25-119">Замена объекта Principal</span><span class="sxs-lookup"><span data-stu-id="48e25-119">Replacing a Principal Object</span></span>](../../../docs/standard/security/replacing-a-principal-object.md)  
- [<span data-ttu-id="48e25-120">Объекты Principal и Identity</span><span class="sxs-lookup"><span data-stu-id="48e25-120">Principal and Identity Objects</span></span>](../../../docs/standard/security/principal-and-identity-objects.md)
