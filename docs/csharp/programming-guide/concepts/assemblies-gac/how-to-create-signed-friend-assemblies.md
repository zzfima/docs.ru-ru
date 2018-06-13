---
title: Практическое руководство. Создание подписанных дружественных сборок (C#)
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: 34243a65f57f41c358439baac82a1ce169233259
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340662"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a><span data-ttu-id="e1d20-102">Практическое руководство. Создание подписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="e1d20-102">How to: Create Signed Friend Assemblies (C#)</span></span>
<span data-ttu-id="e1d20-103">В этом примере демонстрируется использование дружественных сборок со сборками, имеющими строгие имена.</span><span class="sxs-lookup"><span data-stu-id="e1d20-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="e1d20-104">Обе сборки должны иметь строгое имя.</span><span class="sxs-lookup"><span data-stu-id="e1d20-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="e1d20-105">Хотя обе сборки в этом примере используют одинаковые ключи, вы можете использовать для двух сборок разные ключи.</span><span class="sxs-lookup"><span data-stu-id="e1d20-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="e1d20-106">Создание подписанной и дружественной сборки</span><span class="sxs-lookup"><span data-stu-id="e1d20-106">To create a signed assembly and a friend assembly</span></span>  
  
1.  <span data-ttu-id="e1d20-107">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="e1d20-107">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="e1d20-108">Используйте следующую последовательность команд в средстве задания строгих имен для формирования файла ключа и отображения его открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="e1d20-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="e1d20-109">Дополнительные сведения см. на странице [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) (Sn.exe: средство строгих имен).</span><span class="sxs-lookup"><span data-stu-id="e1d20-109">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
    1.  <span data-ttu-id="e1d20-110">Создайте ключ строгого имени для этого примера и сохраните его в файле FriendAssemblies.snk:</span><span class="sxs-lookup"><span data-stu-id="e1d20-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="e1d20-111">Извлеките открытый ключ из FriendAssemblies.snk и поместите его в файл FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="e1d20-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="e1d20-112">Выведите на экран открытый ключ, хранящийся в файле FriendAssemblies.publickey:</span><span class="sxs-lookup"><span data-stu-id="e1d20-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3.  <span data-ttu-id="e1d20-113">Создайте файл C# с именем `friend_signed_A`, содержащий приведенный ниже код.</span><span class="sxs-lookup"><span data-stu-id="e1d20-113">Create a C# file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="e1d20-114">Атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> используется в коде для объявления friend_signed_B в качестве дружественной сборки.</span><span class="sxs-lookup"><span data-stu-id="e1d20-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="e1d20-115">Средство задания строгих имен создает новый открытый ключ при каждом запуске.</span><span class="sxs-lookup"><span data-stu-id="e1d20-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="e1d20-116">Таким образом, необходимо заменить открытый ключ в следующем коде только что созданным открытым ключом, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="e1d20-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4.  <span data-ttu-id="e1d20-117">Скомпилируйте и подпишите сборку friend_signed_A с помощью приведенной ниже команды.</span><span class="sxs-lookup"><span data-stu-id="e1d20-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5.  <span data-ttu-id="e1d20-118">Создайте файл C# с именем `friend_signed_B`, содержащий следующий код.</span><span class="sxs-lookup"><span data-stu-id="e1d20-118">Create a C# file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="e1d20-119">Поскольку сборка friend_signed_A указывает сборку friend_signed_B в качестве дружественной сборки, код в сборке friend_signed_B может обращаться к типам и членам `internal` в сборке friend_signed_A.</span><span class="sxs-lookup"><span data-stu-id="e1d20-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `internal` types and members from friend_signed_A.</span></span> <span data-ttu-id="e1d20-120">Файл содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="e1d20-120">The file contains the following code.</span></span>  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6.  <span data-ttu-id="e1d20-121">Откомпилируйте и подпишите сборку friend_signed_B с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="e1d20-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     <span data-ttu-id="e1d20-122">Имя сборки, созданной компилятором, должно соответствовать имени дружественной сборки, передаваемой атрибуту <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e1d20-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="e1d20-123">Необходимо явно указать имя выходной сборки (EXE или DLL) с помощью параметра компилятора `/out`.</span><span class="sxs-lookup"><span data-stu-id="e1d20-123">You must explicitly specify the name of the output assembly (.exe or .dll) by using the `/out` compiler option.</span></span>  <span data-ttu-id="e1d20-124">Дополнительные сведения см. в разделе [/out (параметры компилятора C#)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e1d20-124">For more information, see [/out (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md).</span></span>  
  
7.  <span data-ttu-id="e1d20-125">Запустите файл friend_signed_B.exe.</span><span class="sxs-lookup"><span data-stu-id="e1d20-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="e1d20-126">Программа выводит строку "Class1.Test".</span><span class="sxs-lookup"><span data-stu-id="e1d20-126">The program prints the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="e1d20-127">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1d20-127">.NET Framework Security</span></span>  
 <span data-ttu-id="e1d20-128">Между атрибутом <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> и классом <xref:System.Security.Permissions.StrongNameIdentityPermission> существует определенное сходство.</span><span class="sxs-lookup"><span data-stu-id="e1d20-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="e1d20-129">Основное отличие заключается в том, что для выполнения <xref:System.Security.Permissions.StrongNameIdentityPermission> в определенном разделе кода могут потребоваться разрешения системы безопасности, тогда как атрибут <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> определяет видимость членов и типов `internal`.</span><span class="sxs-lookup"><span data-stu-id="e1d20-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `internal` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1d20-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e1d20-130">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="e1d20-131">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="e1d20-131">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="e1d20-132">Дружественные сборки (C#)</span><span class="sxs-lookup"><span data-stu-id="e1d20-132">Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/friend-assemblies.md)  
 [<span data-ttu-id="e1d20-133">Практическое руководство. Создание неподписанных дружественных сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="e1d20-133">How to: Create Unsigned Friend Assemblies (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)  
 [<span data-ttu-id="e1d20-134">/keyfile</span><span class="sxs-lookup"><span data-stu-id="e1d20-134">/keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="e1d20-135">Sn.exe (средство строгих имен)</span><span class="sxs-lookup"><span data-stu-id="e1d20-135">Sn.exe (Strong Name Tool)</span></span>](https://msdn.microsoft.com/library/k5b5tt23)  
 [<span data-ttu-id="e1d20-136">Создание и использование сборок со строгими именами</span><span class="sxs-lookup"><span data-stu-id="e1d20-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 [<span data-ttu-id="e1d20-137">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e1d20-137">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)
