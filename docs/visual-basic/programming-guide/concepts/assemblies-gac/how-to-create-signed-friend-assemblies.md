---
title: 'Практическое: Создание подписанных дружественных сборок (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 6a9dcc65e7e496a436d81ad2d311a4174f111104
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188447"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="4242c-102">Практическое: Создание подписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4242c-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="4242c-103">В этом примере демонстрируется использование дружественных сборок со сборками, имеющими строгие имена.</span><span class="sxs-lookup"><span data-stu-id="4242c-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="4242c-104">Обе сборки должны иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="4242c-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="4242c-105">Хотя обе сборки в этом примере используют одинаковые ключи, вы можете использовать для двух сборок разные ключи.</span><span class="sxs-lookup"><span data-stu-id="4242c-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="4242c-106">Создание подписанной и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="4242c-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="4242c-107">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="4242c-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="4242c-108">Используйте следующую последовательность команд в средстве задания строгих имен для формирования файла ключа и отображения его открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="4242c-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="4242c-109">Дополнительные сведения см. в разделе [Sn.exe (средство строгих имен)][Sn.exe (средство строгих имен)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="4242c-109">For more information, see [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="4242c-110">Создайте ключ строгого имени для этого примера и сохраните его в файле FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="4242c-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="4242c-111">Извлеките открытый ключ из FriendAssemblies.snk и поместите его в файл FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="4242c-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="4242c-112">Выведите на экран открытый ключ, хранящийся в файле FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="4242c-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="4242c-113">Создайте файл Visual Basic `friend_signed_A` , содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="4242c-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="4242c-114">Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="4242c-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="4242c-115">Средство задания строгих имен создает новый открытый ключ при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="4242c-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="4242c-116">Таким образом, необходимо заменить открытый ключ в следующем коде только что созданным открытым ключом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4242c-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4.  <span data-ttu-id="4242c-117">Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="4242c-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5.  <span data-ttu-id="4242c-118">Создайте файл Visual Basic с именем `friend_signed_B` и содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="4242c-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="4242c-119">Поскольку сборка friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, код в сборке friend_signed_B может обращаться к типам и членам `Friend` в сборке friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="4242c-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="4242c-120">Файл содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="4242c-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="4242c-121">Откомпилируйте и подпишите сборку friend_signed_B с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="4242c-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="4242c-122">Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4242c-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="4242c-123">Можно явно задать сборку с помощью `-out` параметр компилятора.</span><span class="sxs-lookup"><span data-stu-id="4242c-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="4242c-124">Дополнительные сведения см. в разделе [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span><span class="sxs-lookup"><span data-stu-id="4242c-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7.  <span data-ttu-id="4242c-125">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="4242c-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="4242c-126">Программа отображает строку «Class1.Test».</span><span class="sxs-lookup"><span data-stu-id="4242c-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4242c-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4242c-127">.NET Framework Security</span></span>  
 <span data-ttu-id="4242c-128">Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство.</span><span class="sxs-lookup"><span data-stu-id="4242c-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="4242c-129">Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `Friend`.</span><span class="sxs-lookup"><span data-stu-id="4242c-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4242c-130">См. также</span><span class="sxs-lookup"><span data-stu-id="4242c-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="4242c-131">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4242c-131">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="4242c-132">Дружественные сборки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4242c-132">Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="4242c-133">Практическое: создание неподписанных дружественных сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4242c-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="4242c-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="4242c-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 <span data-ttu-id="4242c-135">[Sn.exe (средство строгих имен)] [Sn.exe (средство строгих имен)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="4242c-135">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="4242c-136">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="4242c-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="4242c-137">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="4242c-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
