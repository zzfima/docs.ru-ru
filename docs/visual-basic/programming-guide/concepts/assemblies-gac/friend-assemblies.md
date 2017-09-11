---
title: "Дружественные сборки (Visual Basic) | Документы Microsoft"
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
ms.assetid: 9b3d5716-e6e4-47a7-a3e9-084d7fba5c28
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 23c9167bf6a632b53202bdc56aebb2248065e967
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="friend-assemblies-visual-basic"></a><span data-ttu-id="14af8-102">Дружественные сборки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14af8-102">Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="14af8-103">Объект *дружественной сборки* — это сборка, можно получить доступ к другой сборке [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) типы и члены.</span><span class="sxs-lookup"><span data-stu-id="14af8-103">A *friend assembly* is an assembly that can access another assembly's [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) types and members.</span></span> <span data-ttu-id="14af8-104">Если вы сборка определена как дружественная сборка, необходимо больше не помечать типы и члены как открытые, чтобы они доступны в других сборках.</span><span class="sxs-lookup"><span data-stu-id="14af8-104">If you identify an assembly as a friend assembly, you no longer have to mark types and members as public in order for them to be accessed by other assemblies.</span></span> <span data-ttu-id="14af8-105">Это особенно удобно в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="14af8-105">This is especially convenient in the following scenarios:</span></span>  
  
-   <span data-ttu-id="14af8-106">Во время модульного тестирования, когда код теста выполняется в отдельной сборке, но требует доступ к членам в тестируемой сборке, которые помечены как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="14af8-106">During unit testing, when test code runs in a separate assembly but requires access to members in the assembly being tested that are marked as `Friend`.</span></span>  
  
-   <span data-ttu-id="14af8-107">Если разрабатывается библиотека классов, и дополнения к библиотеке содержатся в отдельных сборках, но требуют доступа к членам в существующих сборках, которые помечены как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="14af8-107">When you are developing a class library and additions to the library are contained in separate assemblies but require access to members in existing assemblies that are marked as `Friend`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14af8-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="14af8-108">Remarks</span></span>  
 <span data-ttu-id="14af8-109">Можно использовать <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибутом опознания дружественных сборок для данной сборки.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="14af8-109">You can use the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to identify one or more friend assemblies for a given assembly.</span></span> <span data-ttu-id="14af8-110">В следующем примере используется <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>в сборке A и задающий сборку `AssemblyB` как дружественную сборку.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="14af8-110">The following example uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute in assembly A and specifies assembly `AssemblyB` as a friend assembly.</span></span> <span data-ttu-id="14af8-111">Это позволяет сборке `AssemblyB` доступ ко всем типам и членам в сборке, которые помечены как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="14af8-111">This gives assembly `AssemblyB` access to all types and members in assembly A that are marked as `Friend`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14af8-112">При компиляции сборки (сборка `AssemblyB`) для доступа к внутренним типам и членам другой сборки (сборка *A*), необходимо явно указать имя выходного файла (.exe или .dll) с помощью **/out** параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="14af8-112">When you compile an assembly (assembly `AssemblyB`) that will access internal types or internal members of another assembly (assembly *A*), you must explicitly specify the name of the output file (.exe or .dll) by using the **/out** compiler option.</span></span> <span data-ttu-id="14af8-113">Это необходимо, потому что компилятор еще не создал имя сборки, который создается во время его привязки к внешним ссылкам.</span><span class="sxs-lookup"><span data-stu-id="14af8-113">This is required because the compiler has not yet generated the name for the assembly it is building at the time it is binding to external references.</span></span> <span data-ttu-id="14af8-114">Дополнительные сведения см. в разделе [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="14af8-114">For more information, see [/out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports System  
<Assembly: InternalsVisibleTo("AssemblyB")>   
  
' Friend class.  
Friend Class FriendClass  
    Public Sub Test()  
        Console.WriteLine("Sample Class")  
    End Sub  
End Class  
  
' Public class with a Friend method.  
Public Class ClassWithFriendMethod  
    Friend Sub Test()  
        Console.WriteLine("Sample Method")  
    End Sub  
End Class  
  
```  
  
 <span data-ttu-id="14af8-115">Только сборки, которые явным образом указаны как дружественные можно получить доступ к `Friend` типы и члены.</span><span class="sxs-lookup"><span data-stu-id="14af8-115">Only assemblies that you explicitly specify as friends can access `Friend` types and members.</span></span> <span data-ttu-id="14af8-116">Например, если сборка B является дружественной для сборки A и сборка C ссылается на сборку B, C не имеет доступа к `Friend` типы в сборке A.</span><span class="sxs-lookup"><span data-stu-id="14af8-116">For example, if assembly B is a friend of assembly A and assembly C references assembly B, C does not have access to `Friend` types in A.</span></span>  
  
 <span data-ttu-id="14af8-117">Компилятор выполняет некоторые основные проверки имя дружественной сборки, передаваемый <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="14af8-117">The compiler performs some basic validation of the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="14af8-118">Если сборка *A* объявляет *B* как дружественную сборку, правила проверки, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="14af8-118">If assembly *A* declares *B* as a friend assembly, the validation rules are as follows:</span></span>  
  
-   <span data-ttu-id="14af8-119">Если сборка *A* имеет строгое имя сборки *B* также должна иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="14af8-119">If assembly *A* is strong named, assembly *B* must also be strong named.</span></span> <span data-ttu-id="14af8-120">Имя дружественной сборки, передаваемое атрибут должен состоять из имени сборки и открытого ключа строгого имени ключа, который используется для подписи сборки *B*.</span><span class="sxs-lookup"><span data-stu-id="14af8-120">The friend assembly name that is passed to the attribute must consist of the assembly name and the public key of the strong-name key that is used to sign assembly *B*.</span></span>  
  
     <span data-ttu-id="14af8-121">Имя дружественной сборки, передаваемое <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>атрибут не может быть строгое имя сборки *B*: не включайте версии сборки, языка и региональных параметров, архитектуры или маркера открытого ключа.</xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="14af8-121">The friend assembly name that is passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute cannot be the strong name of assembly *B*: do not include the assembly version, culture, architecture, or public key token.</span></span>  
  
-   <span data-ttu-id="14af8-122">Если сборка *A* не имеет строгого имени, имя дружественной сборки должно состоять из имени сборки.</span><span class="sxs-lookup"><span data-stu-id="14af8-122">If assembly *A* is not strong named, the friend assembly name should consist of only the assembly name.</span></span> <span data-ttu-id="14af8-123">Дополнительные сведения см. в разделе [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="14af8-123">For more information, see [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md).</span></span>  
  
-   <span data-ttu-id="14af8-124">Если сборка *B* имеет строгое имя, необходимо указать ключ строгого имени для сборки *B* с помощью параметра проекта или командной строки `/keyfile` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="14af8-124">If assembly *B* is strong named, you must specify the strong-name key for assembly *B* by using the project setting or the command-line `/keyfile` compiler option.</span></span> <span data-ttu-id="14af8-125">Дополнительные сведения см. в разделе [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="14af8-125">For more information, see [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md).</span></span>  
  
 <span data-ttu-id="14af8-126"><xref:System.Security.Permissions.StrongNameIdentityPermission>Класс также предоставляет возможность совместного использования типов, со следующими отличиями:</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="14af8-126">The <xref:System.Security.Permissions.StrongNameIdentityPermission> class also provides the ability to share types, with the following differences:</span></span>  
  
-   <span data-ttu-id="14af8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission>применяется к отдельному типу, а Дружественная сборка применяется ко всей сборке.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="14af8-127"><xref:System.Security.Permissions.StrongNameIdentityPermission> applies to an individual type, while a friend assembly applies to the whole assembly.</span></span>  
  
-   <span data-ttu-id="14af8-128">Если существуют сотни типы в сборке *A* , вы хотите совместно использовать со сборкой *B*, необходимо добавить <xref:System.Security.Permissions.StrongNameIdentityPermission>для всех приложений.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="14af8-128">If there are hundreds of types in assembly *A* that you want to share with assembly *B*, you have to add <xref:System.Security.Permissions.StrongNameIdentityPermission> to all of them.</span></span> <span data-ttu-id="14af8-129">Если используется Дружественная сборка, достаточно один раз объявить дружественные отношения.</span><span class="sxs-lookup"><span data-stu-id="14af8-129">If you use a friend assembly, you only need to declare the friend relationship once.</span></span>  
  
-   <span data-ttu-id="14af8-130">При использовании <xref:System.Security.Permissions.StrongNameIdentityPermission>, вы хотите поделиться типы должны быть объявлены как открытые.</xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="14af8-130">If you use <xref:System.Security.Permissions.StrongNameIdentityPermission>, the types you want to share have to be declared as public.</span></span> <span data-ttu-id="14af8-131">При использовании дружественной сборки общие типы объявляются как `Friend`.</span><span class="sxs-lookup"><span data-stu-id="14af8-131">If you use a friend assembly, the shared types are declared as `Friend`.</span></span>  
  
 <span data-ttu-id="14af8-132">Сведения о том, как обращаться к сборке `Friend` типы и методы из файла модуля (файл с расширением .netmodule), в разделе [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span><span class="sxs-lookup"><span data-stu-id="14af8-132">For information about how to access an assembly's `Friend` types and methods from a module file (a file with the .netmodule extension), see [/moduleassemblyname (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14af8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="14af8-133">See Also</span></span>  
 <span data-ttu-id="14af8-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span><span class="sxs-lookup"><span data-stu-id="14af8-134"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute></span></span>   
 <span data-ttu-id="14af8-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></xref:System.Security.Permissions.StrongNameIdentityPermission></span><span class="sxs-lookup"><span data-stu-id="14af8-135"><xref:System.Security.Permissions.StrongNameIdentityPermission></span></span>   
<span data-ttu-id="14af8-136"> [Практическое руководство: создание неподписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="14af8-136"> [How to: Create Unsigned Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md) </span></span>  
<span data-ttu-id="14af8-137"> [Практическое руководство: Создание подписанных дружественных сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="14af8-137"> [How to: Create Signed Friend Assemblies (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-signed-friend-assemblies.md) </span></span>  
<span data-ttu-id="14af8-138"> [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="14af8-138"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="14af8-139"> [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)</span><span class="sxs-lookup"><span data-stu-id="14af8-139"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md)</span></span>
