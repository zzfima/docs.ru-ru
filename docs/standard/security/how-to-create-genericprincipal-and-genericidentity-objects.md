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
ms.openlocfilehash: 37f5543ceaca83a024132c5d010b6d969876454f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353828"
---
# <a name="how-to-create-genericprincipal-and-genericidentity-objects"></a>Практическое руководство. Создание объектов GenericPrincipal и GenericIdentity

Класс <xref:System.Security.Principal.GenericIdentity> можно использовать совместно с классом <xref:System.Security.Principal.GenericPrincipal> для создания схемы авторизации, которая существует независимо от домена Windows.

### <a name="to-create-a-genericprincipal-object"></a>Создание объекта GenericPrincipal

1. Создайте новый экземпляр класса identity и инициализируйте его с необходимым именем. Следующий код создает новый объект **GenericIdentity** и инициализирует его с именем `MyUser`.

    ```vb
    Dim myIdentity As New GenericIdentity("MyUser")
    ```

    ```csharp
    GenericIdentity myIdentity = new GenericIdentity("MyUser");
    ```

2. Создайте новый экземпляр класса **GenericPrincipal** и инициализируйте его с ранее созданным объектом **GenericIdentity** и массивом строк, представляющими роли, которые требуется связать с этим участником. В следующем примере кода задается массив строк, представляющих роль администратора и роль пользователя. Затем **GenericPrincipal** инициализируется с предыдущим **GenericIdentity** и массивом строк.

    ```vb
    Dim myStringArray As String() = {"Manager", "Teller"}
    DIm myPrincipal As New GenericPrincipal(myIdentity, myStringArray)
    ```

    ```csharp
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal = new GenericPrincipal(myIdentity, myStringArray);
    ```

3. Для подключения участника к текущему потоку используйте следующий код. Это полезно в ситуациях, когда участник должен проверяться несколько раз, он должен быть проверен другим кодом, выполняемым в приложении, или его необходимо проверить с помощью объекта <xref:System.Security.Permissions.PrincipalPermission>. Объект Principal по-прежнему можно проверять на основании ролей без подключения его к потоку. Дополнительные сведения см. в разделе [Замена объекта Principal](../../../docs/standard/security/replacing-a-principal-object.md).

    ```vb
    Thread.CurrentPrincipal = myPrincipal
    ```

    ```csharp
    Thread.CurrentPrincipal = myPrincipal;
    ```

## <a name="example"></a>Пример

В следующем примере кода показано, как создать экземпляр объекта **GenericPrincipal** и **GenericIdentity**. Данный код выводит значения этих объектов на консоль.

```vb
Imports System.Security.Principal
Imports System.Threading

Public Class Class1

    Public Shared Sub Main()
        ' Create generic identity.
        Dim myIdentity As New GenericIdentity("MyIdentity")

        ' Create generic principal.
        Dim myStringArray As String() =  {"Manager", "Teller"}
        Dim myPrincipal As New GenericPrincipal(myIdentity, myStringArray)

        ' Attach the principal to the current thread.
        ' This is not required unless repeated validation must occur,
        ' other code in your application must validate, or the
        ' PrincipalPermission object is used.
        Thread.CurrentPrincipal = myPrincipal

        ' Print values to the console.
        Dim name As String = myPrincipal.Identity.Name
        Dim auth As Boolean = myPrincipal.Identity.IsAuthenticated
        Dim isInRole As Boolean = myPrincipal.IsInRole("Manager")

        Console.WriteLine("The name is: {0}", name)
        Console.WriteLine("The isAuthenticated is: {0}", auth)
        Console.WriteLine("Is this a Manager? {0}", isInRole)

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
    GenericIdentity myIdentity = new GenericIdentity("MyIdentity");

    // Create generic principal.
    String[] myStringArray = {"Manager", "Teller"};
    GenericPrincipal myPrincipal =
        new GenericPrincipal(myIdentity, myStringArray);

    // Attach the principal to the current thread.
    // This is not required unless repeated validation must occur,
    // other code in your application must validate, or the
    // PrincipalPermission object is used.
    Thread.CurrentPrincipal = myPrincipal;

    // Print values to the console.
    String name =  myPrincipal.Identity.Name;
    bool auth =  myPrincipal.Identity.IsAuthenticated;
    bool isInRole =  myPrincipal.IsInRole("Manager");

    Console.WriteLine("The name is: {0}", name);
    Console.WriteLine("The isAuthenticated is: {0}", auth);
    Console.WriteLine("Is this a Manager? {0}", isInRole);

    return 0;
    }
}
```

Во время выполнения приложение выводит примерно следующие сведения.

```console
The Name is: MyIdentity
The IsAuthenticated is: True
Is this a Manager? True
```

## <a name="see-also"></a>См. также

- <xref:System.Security.Principal.GenericIdentity>
- <xref:System.Security.Principal.GenericPrincipal>
- <xref:System.Security.Permissions.PrincipalPermission>
- [Замена объекта Principal](../../../docs/standard/security/replacing-a-principal-object.md)
- [Объекты Principal и Identity](../../../docs/standard/security/principal-and-identity-objects.md)
