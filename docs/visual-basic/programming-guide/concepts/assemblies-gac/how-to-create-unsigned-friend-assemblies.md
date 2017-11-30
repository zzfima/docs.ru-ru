---
title: "Как: создание неподписанных дружественных сборок (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a2b2667c60a07a2897a0934d210901042e2e43c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="c4c53-102">Как: создание неподписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4c53-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="c4c53-103">В этом примере показано использование дружественных сборок с неподписанными сборками.</span><span class="sxs-lookup"><span data-stu-id="c4c53-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="c4c53-104">Создание сборки и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="c4c53-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="c4c53-105">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="c4c53-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="c4c53-106">Создайте файл Visual Basic с именем `friend_signed_A.` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="c4c53-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="c4c53-107">Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="c4c53-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
    ```vb  
    ' friend_unsigned_A.vb  
    ' Compile with:   
    ' Vbc /target:library friend_unsigned_A.vb  
    Imports System.Runtime.CompilerServices  
    Imports System  
  
    <Assembly: InternalsVisibleTo("friend_unsigned_B")>   
  
    ' Friend type.  
    Friend Class Class1  
        Public Sub Test()  
            Console.WriteLine("Class1.Test")  
        End Sub  
    End Class  
  
    ' Public type with Friend member.  
    Public Class Class2  
        Friend Sub Test()  
            Console.WriteLine("Class2.Test")  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="c4c53-108">Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c4c53-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="c4c53-109">Создайте файл Visual Basic с именем `friend_unsigned_B` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="c4c53-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="c4c53-110">Так как файл friend_unsigned_A задает friend_unsigned_B в качестве дружественной сборки, код friend_unsigned_B может обращаться к типам и членам `Friend` из friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="c4c53-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
    ```vb  
    ' friend_unsigned_B.vb  
    ' Compile with:   
    ' Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    Module Module1  
        Sub Main()  
            ' Access a Friend type.  
            Dim inst1 As New Class1()  
            inst1.Test()  
  
            Dim inst2 As New Class2()  
            ' Access a Friend member of a public type.  
            inst2.Test()  
  
            System.Console.ReadLine()  
        End Sub  
    End Module  
    ```  
  
5.  <span data-ttu-id="c4c53-111">Скомпилируйте сборку friend_signed_B с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="c4c53-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="c4c53-112">Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c4c53-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="c4c53-113">Можно явно задать сборку с помощью `/out` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="c4c53-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="c4c53-114">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="c4c53-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="c4c53-115">Программа выведет две строки: "Class1.Test" и "Class2.Test".</span><span class="sxs-lookup"><span data-stu-id="c4c53-115">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c4c53-116">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="c4c53-116">.NET Framework Security</span></span>  
 <span data-ttu-id="c4c53-117">Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство.</span><span class="sxs-lookup"><span data-stu-id="c4c53-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="c4c53-118">Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `Friend`.</span><span class="sxs-lookup"><span data-stu-id="c4c53-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c53-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c4c53-119">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="c4c53-120">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4c53-120">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="c4c53-121">Дружественные сборки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4c53-121">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="c4c53-122">Как: Создание подписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4c53-122">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md)  
 [<span data-ttu-id="c4c53-123">Основные понятия о программировании руководства</span><span class="sxs-lookup"><span data-stu-id="c4c53-123">Programming Guide Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
