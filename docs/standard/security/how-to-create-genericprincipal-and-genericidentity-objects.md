---
title: "How to: Create GenericPrincipal and GenericIdentity Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Creating Generic Identity Objects"
  - "GenericPrincipal Objects"
  - "Creating GenericPrincipal Objects"
  - "GenericIdentity Objects"
ms.assetid: 465694cf-258b-4747-9dae-35b01a5bcdbb
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Create GenericPrincipal and GenericIdentity Objects
Класс <xref:System.Security.Principal.GenericIdentity> можно использовать совместно с классом <xref:System.Security.Principal.GenericPrincipal> для создания схемы авторизации, существующей независимо от домена Windows NT или Windows 2000.  
  
### Создание объекта GenericPrincipal  
  
1.  Создайте новый экземпляр класса Identity и инициализируйте его с требуемым именем.  В следующем фрагменте кода создается новый объект **GenericIdentity** с именем `MyUser`.  
  
    ```vb  
    Dim MyIdentity As New GenericIdentity("MyUser")  
    ```  
  
    ```csharp  
    GenericIdentity MyIdentity = new GenericIdentity("MyUser");  
    ```  
  
2.  Создайте новый экземпляр класса **GenericPrincipal** и инициализируйте его с помощью созданного ранее объекта **GenericIdentity** и массива строк, представляющих роли, которые необходимо связать с этим участником.  В следующем примере кода определяется массив строк, который представляет роль администратора и роль пользователя.  Далее объект **GenericPrincipal** инициализируется с помощью ранее созданного объекта **GenericIdentity** и строкового массива.  
  
    ```vb  
    Dim MyStringArray As String() = {"Manager", "Teller"}  
    DIm MyPrincipal As New GenericPrincipal(MyIdentity, MyStringArray)  
    ```  
  
    ```csharp  
    String[] MyStringArray = {"Manager", "Teller"};  
    GenericPrincipal MyPrincipal = new GenericPrincipal(MyIdentity, MyStringArray);  
    ```  
  
3.  Подключите участника к текущему потоку с помощью следующего кода.  Это полезно в ситуациях, когда участник либо должен быть проверен несколько раз, либо он должен быть проверен другим программным кодом, запущенным в данном приложении, либо он должен быть проверен объектом <xref:System.Security.Permissions.PrincipalPermission>.  Выполнять проверку объекта\-участника на основе ролей можно и без подключения его к потоку.  Дополнительные сведения см. в разделе [Замена объекта\-участника](../../../docs/standard/security/replacing-a-principal-object.md).  
  
    ```vb  
    Thread.CurrentPrincipal = MyPrincipal  
    ```  
  
    ```csharp  
    Thread.CurrentPrincipal = MyPrincipal;  
    ```  
  
## Пример  
 В следующем примере кода демонстрируется создание экземпляров объектов **GenericPrincipal** и **GenericIdentity**.  Этот код выводит на консоль значения этих объектов.  
  
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
  
 По завершении выполнения приложение выводит текст, подобный следующему:  
  
```  
The Name is: MyIdentity  
The IsAuthenticated is: True  
Is this a Manager? True  
```  
  
## См. также  
 <xref:System.Security.Principal.GenericIdentity>   
 <xref:System.Security.Principal.GenericPrincipal>   
 <xref:System.Security.Permissions.PrincipalPermission>   
 [Replacing a Principal Object](../../../docs/standard/security/replacing-a-principal-object.md)   
 [Principal and Identity Objects](../../../docs/standard/security/principal-and-identity-objects.md)