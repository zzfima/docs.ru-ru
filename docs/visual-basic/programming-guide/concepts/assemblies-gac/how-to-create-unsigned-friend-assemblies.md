---
title: "Практическое руководство: создание неподписанных дружественных сборок (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 5735eb79-9729-4c46-ac1f-537ada3acaa7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d184b5d6f8334df46351d3f2974f1fb91e54a492
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-unsigned-friend-assemblies-visual-basic"></a><span data-ttu-id="a2d36-102">Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2d36-102">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="a2d36-103">В этом примере показано использование дружественных сборок с неподписанными сборками.</span><span class="sxs-lookup"><span data-stu-id="a2d36-103">This example shows how to use friend assemblies with assemblies that are unsigned.</span></span>  
  
### <a name="to-create-an-assembly-and-a-friend-assembly"></a><span data-ttu-id="a2d36-104">Для создания сборки и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="a2d36-104">To create an assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="a2d36-105">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="a2d36-105">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="a2d36-106">Создайте файл Visual Basic с именем `friend_signed_A.` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="a2d36-106">Create a Visual Basic file named `friend_signed_A.` that contains the following code.</span></span> <span data-ttu-id="a2d36-107">Код использует <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут для объявления friend_signed_B в качестве дружественной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a2d36-107">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
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
  
3.  <span data-ttu-id="a2d36-108">Откомпилируйте и подпишите сборку friend_signed_A с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="a2d36-108">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```vb  
    Vbc /target:library friend_unsigned_A.vb  
    ```  
  
4.  <span data-ttu-id="a2d36-109">Создайте файл Visual Basic с именем `friend_unsigned_B` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="a2d36-109">Create a Visual Basic file named `friend_unsigned_B` that contains the following code.</span></span> <span data-ttu-id="a2d36-110">Поскольку friend_unsigned_A friend_unsigned_B указывает в качестве дружественной сборки, код в friend_unsigned_B можно получить доступ к `Friend` типов и членов из friend_unsigned_A.</span><span class="sxs-lookup"><span data-stu-id="a2d36-110">Because friend_unsigned_A specifies friend_unsigned_B as a friend assembly, the code in friend_unsigned_B can access `Friend` types and members from friend_unsigned_A.</span></span>  
  
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
  
5.  <span data-ttu-id="a2d36-111">Откомпилируйте сборку friend_signed_B с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="a2d36-111">Compile friend_signed_B by using the following command.</span></span>  
  
    ```vb  
    Vbc /r:friend_unsigned_A.dll friend_unsigned_B.vb  
    ```  
  
     <span data-ttu-id="a2d36-112">Имя сборки, созданных компилятором должно совпадать имя дружественной сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a2d36-112">The name of the assembly that is generated by the compiler must match the friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="a2d36-113">Можно явно задать сборку, используя `/out` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="a2d36-113">You can explicitly set the assembly by using the `/out` compiler option.</span></span>  
  
6.  <span data-ttu-id="a2d36-114">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="a2d36-114">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="a2d36-115">Программа выводит две строки: «Class1.Test» и «Class2.Test».</span><span class="sxs-lookup"><span data-stu-id="a2d36-115">The program prints two strings: "Class1.Test" and "Class2.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a2d36-116">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a2d36-116">.NET Framework Security</span></span>  
 <span data-ttu-id="a2d36-117">Существует сходство между <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом и <xref:System.Security.Permissions.StrongNameIdentityPermission>класса.</xref:System.Security.Permissions.StrongNameIdentityPermission> </xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a2d36-117">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="a2d36-118">Основное различие заключается в, <xref:System.Security.Permissions.StrongNameIdentityPermission>может потребовать разрешения безопасности для выполнения определенного раздела кода, тогда как <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут управляет видимостью `Friend` типы и члены.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> </xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="a2d36-118">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d36-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a2d36-119">See Also</span></span>  
 <span data-ttu-id="a2d36-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="a2d36-120"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
<span data-ttu-id="a2d36-121"> [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="a2d36-121"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="a2d36-122"> [Дружественные сборки (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a2d36-122"> [Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md) </span></span>  
<span data-ttu-id="a2d36-123"> [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="a2d36-123"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="a2d36-124"> [Основные понятия программирования руководство](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="a2d36-124"> [Programming Guide Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
