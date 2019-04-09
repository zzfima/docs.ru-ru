---
title: Использование метода Assert
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- granting permissions, overriding security checks
- code access security, overriding security checks
- overriding security checks
- security [.NET Framework], overriding security checks
- security [.NET Framework], assertions
- asserted permissions
- Assert method
- caller security checks
- permissions [.NET Framework], overriding security checks
- permissions [.NET Framework], assertions
ms.assetid: 1e40f4d3-fb7d-4f19-b334-b6076d469ea9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 08b46d96f9fb950602766639559a375a25747010
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073732"
---
# <a name="using-the-assert-method"></a><span data-ttu-id="f993b-102">Использование метода Assert</span><span class="sxs-lookup"><span data-stu-id="f993b-102">Using the Assert Method</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <xref:System.Security.CodeAccessPermission.Assert%2A> <span data-ttu-id="f993b-103">— Это метод, который может вызываться для классов разрешений доступа к коду и на <xref:System.Security.PermissionSet> класса.</span><span class="sxs-lookup"><span data-stu-id="f993b-103">is a method that can be called on code access permission classes and on the <xref:System.Security.PermissionSet> class.</span></span> <span data-ttu-id="f993b-104">Можно использовать **Assert** для реализации кода (и подчиненным вызывающим объектам) для выполнения действий, которые коде есть соответствующие разрешения, но его вызывающих отсутствует разрешение для выполнения.</span><span class="sxs-lookup"><span data-stu-id="f993b-104">You can use **Assert** to enable your code (and downstream callers) to perform actions that your code has permission to do but its callers might not have permission to do.</span></span> <span data-ttu-id="f993b-105">Утверждение безопасности изменяет нормальный ход процесса, которому следует среда выполнения при проверке безопасности.</span><span class="sxs-lookup"><span data-stu-id="f993b-105">A security assertion changes the normal process that the runtime performs during a security check.</span></span> <span data-ttu-id="f993b-106">Когда вы утверждаете разрешение, система безопасности не проверяет вызывающие объекты кода на наличие утвержденного разрешения.</span><span class="sxs-lookup"><span data-stu-id="f993b-106">When you assert a permission, it tells the security system not to check the callers of your code for the asserted permission.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f993b-107">Используйте утверждения осторожно, так как они могут открывать бреши в системе безопасности и подорвать работу механизма применения ограничений безопасности в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="f993b-107">Use assertions carefully because they can open security holes and undermine the runtime's mechanism for enforcing security restrictions.</span></span>  
  
 <span data-ttu-id="f993b-108">Утверждения удобны в ситуациях, когда библиотека вызывает неуправляемый код или совершает вызов, требующий разрешение, связь которого с назначением библиотеки не очевидна.</span><span class="sxs-lookup"><span data-stu-id="f993b-108">Assertions are useful in situations in which a library calls into unmanaged code or makes a call that requires a permission that is not obviously related to the library's intended use.</span></span> <span data-ttu-id="f993b-109">Например, весь управляемый код, который выполняет вызовы неуправляемого кода должен иметь **SecurityPermission** с **UnmanagedCode** значений флагов stateful.</span><span class="sxs-lookup"><span data-stu-id="f993b-109">For example, all managed code that calls into unmanaged code must have **SecurityPermission** with the **UnmanagedCode** flag specified.</span></span> <span data-ttu-id="f993b-110">Код, источником которого не является локальный компьютер, например код, скачанный из локальной интрасети, не получает это разрешение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f993b-110">Code that does not originate from the local computer, such as code that is downloaded from the local intranet, will not be granted this permission by default.</span></span> <span data-ttu-id="f993b-111">Таким образом, чтобы код, загруженный из локальной интрасети, мог вызывать библиотеку, использующую неуправляемый код, он должен иметь утвержденное библиотекой разрешение.</span><span class="sxs-lookup"><span data-stu-id="f993b-111">Therefore, in order for code that is downloaded from the local intranet to be able to call a library that uses unmanaged code, it must have the permission asserted by the library.</span></span> <span data-ttu-id="f993b-112">Кроме того, некоторые библиотеки могут выполнять вызовы, которые не видны вызывающим объектам и требуют специальных разрешений.</span><span class="sxs-lookup"><span data-stu-id="f993b-112">Additionally, some libraries might make calls that are unseen to callers and require special permissions.</span></span>  
  
 <span data-ttu-id="f993b-113">Утверждения также можно использовать в ситуациях, когда код обращается к ресурсу способом, полностью скрытым от вызывающих объектов.</span><span class="sxs-lookup"><span data-stu-id="f993b-113">You can also use assertions in situations in which your code accesses a resource in a way that is completely hidden from callers.</span></span> <span data-ttu-id="f993b-114">Предположим, например, что ваша библиотека получает сведения из базы данных, но в процессе также считывает информацию из реестра компьютера.</span><span class="sxs-lookup"><span data-stu-id="f993b-114">For example, suppose your library acquires information from a database, but in the process also reads information from the computer registry.</span></span> <span data-ttu-id="f993b-115">Так как разработчики, использующие вашу библиотеку нет доступа к источнику, они не имеют возможности узнать, что их код должен иметь **RegistryPermission** для использования вашего кода.</span><span class="sxs-lookup"><span data-stu-id="f993b-115">Because developers using your library do not have access to your source, they have no way of knowing that their code requires **RegistryPermission** in order to use your code.</span></span> <span data-ttu-id="f993b-116">Если в такой ситуации вы решите, что неразумно или нерационально требовать наличия разрешения на доступ к реестру у вызывающих ваш код объектов, можно утвердить разрешение на чтение из реестра.</span><span class="sxs-lookup"><span data-stu-id="f993b-116">In this case, if you decide that it is not reasonable or necessary to require that callers of your code have permission to access the registry, you can assert permission for reading the registry.</span></span> <span data-ttu-id="f993b-117">В этом случае он подходит для библиотеки, чтобы подтвердить это разрешение, вызывающие объекты без **RegistryPermission** можно использовать библиотеку.</span><span class="sxs-lookup"><span data-stu-id="f993b-117">In this situation, it is appropriate for the library to assert the permission so that callers without **RegistryPermission** can use the library.</span></span>  
  
 <span data-ttu-id="f993b-118">Утверждение влияет на обход стека только в том случае, если утвержденное разрешение и разрешение, затребованное подчиненным вызывающим объектом, имеют один и тот же тип, а запрошенное разрешение является подмножеством утвержденного разрешения.</span><span class="sxs-lookup"><span data-stu-id="f993b-118">The assertion affects the stack walk only if the asserted permission and a permission demanded by a downstream caller are of the same type and if the demanded permission is a subset of the asserted permission.</span></span> <span data-ttu-id="f993b-119">Например, если вы утверждаете **FileIOPermission** для чтения всех файлов на диске C, а подчиненный выполняется **FileIOPermission** читать C:\Temp, утверждение может повлиять на обход стека; Тем не менее если было для **FileIOPermission** для записи на диск C, утверждение не окажет никакого влияния.</span><span class="sxs-lookup"><span data-stu-id="f993b-119">For example, if you assert **FileIOPermission** to read all files on the C drive, and a downstream demand is made for **FileIOPermission** to read files in C:\Temp, the assertion could affect the stack walk; however, if the demand was for **FileIOPermission** to write to the C drive, the assertion would have no effect.</span></span>  
  
 <span data-ttu-id="f993b-120">Для выполнения утверждений коду должно быть назначено как разрешение, которое вы утверждаете, так и разрешение <xref:System.Security.Permissions.SecurityPermission>, представляющее право на выполнение утверждений.</span><span class="sxs-lookup"><span data-stu-id="f993b-120">To perform assertions, your code must be granted both the permission you are asserting and the <xref:System.Security.Permissions.SecurityPermission> that represents the right to make assertions.</span></span> <span data-ttu-id="f993b-121">Хотя вы и можете утвердить разрешение, которое не было предоставлено коду, такое утверждение будет бессмысленным, так как проверка безопасности завершится со сбоем до того, как такое утверждение могло бы поспособствовать ее успешному завершению.</span><span class="sxs-lookup"><span data-stu-id="f993b-121">Although you could assert a permission that your code has not been granted, the assertion would be pointless because the security check would fail before the assertion could cause it to succeed.</span></span>  
  
 <span data-ttu-id="f993b-122">На следующем рисунке показано, что происходит при использовании **Assert**.</span><span class="sxs-lookup"><span data-stu-id="f993b-122">The following illustration shows what happens when you use **Assert**.</span></span> <span data-ttu-id="f993b-123">Предположим, что справедливы следующие утверждения о сборках A, B, C, E и F, а также разрешениях P1 и P1A:</span><span class="sxs-lookup"><span data-stu-id="f993b-123">Assume that the following statements are true about assemblies A, B, C, E, and F, and two permissions, P1 and P1A:</span></span>  
  
-   <span data-ttu-id="f993b-124">P1A предоставляет право чтения TXT-файлов на диске C.</span><span class="sxs-lookup"><span data-stu-id="f993b-124">P1A represents the right to read .txt files on the C drive.</span></span>  
  
-   <span data-ttu-id="f993b-125">P1 предоставляет право чтения всех файлов на диске C.</span><span class="sxs-lookup"><span data-stu-id="f993b-125">P1 represents the right to read all files on the C drive.</span></span>  
  
-   <span data-ttu-id="f993b-126">P1A и P1 **FileIOPermission** , а P1A является подмножеством P1.</span><span class="sxs-lookup"><span data-stu-id="f993b-126">P1A and P1 are both **FileIOPermission** types, and P1A is a subset of P1.</span></span>  
  
-   <span data-ttu-id="f993b-127">Сборкам E и F назначено разрешение P1A.</span><span class="sxs-lookup"><span data-stu-id="f993b-127">Assemblies E and F have been granted P1A permission.</span></span>  
  
-   <span data-ttu-id="f993b-128">Сборке C назначено разрешение P1.</span><span class="sxs-lookup"><span data-stu-id="f993b-128">Assembly C has been granted P1 permission.</span></span>  
  
-   <span data-ttu-id="f993b-129">Сборкам A и B не назначено ни разрешение P1, ни разрешение P1A.</span><span class="sxs-lookup"><span data-stu-id="f993b-129">Assemblies A and B have been granted neither P1 nor P1A permissions.</span></span>  
  
-   <span data-ttu-id="f993b-130">Метод A содержится в сборке A, метод B содержится в сборке B и т. д.</span><span class="sxs-lookup"><span data-stu-id="f993b-130">Method A is contained in assembly A, method B is contained in assembly B, and so on.</span></span>  
  
 ![Схема, показывающая сборки метода Assert.](./media/using-the-assert-method/assert-method-assemblies.gif)    
  
 <span data-ttu-id="f993b-132">В этом сценарии, метод A вызывает B, B вызывает C, C вызывает E и E вызывает F. метод C утверждает разрешение на чтение файлов на диске C (разрешение P1), а метод E запрашивает разрешения на чтение TXT-файлов на диске C (разрешение P1A).</span><span class="sxs-lookup"><span data-stu-id="f993b-132">In this scenario, method A calls B, B calls C, C calls E, and E calls F. Method C asserts permission to read files on the C drive (permission P1), and method E demands permission to read .txt files on the C drive (permission P1A).</span></span> <span data-ttu-id="f993b-133">Когда требование из F обнаруживается во время выполнения, обход стека для проверки разрешений всех вызывающих объектов F, начиная с E. E разрешение P1A, поэтому обход стека продолжается для проверки разрешений у C, где обнаруживается утверждение для.</span><span class="sxs-lookup"><span data-stu-id="f993b-133">When the demand in F is encountered at run time, a stack walk is performed to check the permissions of all callers of F, starting with E. E has been granted P1A permission, so the stack walk proceeds to examine the permissions of C, where C's assertion is discovered.</span></span> <span data-ttu-id="f993b-134">Так как запрошенное разрешение (P1A) является подмножеством утвержденного разрешения (P1), обход стека останавливается, а проверка безопасности завершается успешно.</span><span class="sxs-lookup"><span data-stu-id="f993b-134">Because the demanded permission (P1A) is a subset of the asserted permission (P1), the stack walk stops and the security check automatically succeeds.</span></span> <span data-ttu-id="f993b-135">То, что разрешение P1A не было назначено сборкам A и B, не имеет никакого значения.</span><span class="sxs-lookup"><span data-stu-id="f993b-135">It does not matter that assemblies A and B have not been granted permission P1A.</span></span> <span data-ttu-id="f993b-136">Утверждая P1, метод C позволяет вызывающим объектам обращаться к ресурсу, защищенному при помощи P1, даже если вызывающие объекты не имеют разрешения на доступ к этому ресурсу.</span><span class="sxs-lookup"><span data-stu-id="f993b-136">By asserting P1, method C ensures that its callers can access the resource protected by P1, even if the callers have not been granted permission to access that resource.</span></span>  
  
 <span data-ttu-id="f993b-137">Если вы разрабатываете библиотеку классов и класс обращается к защищенному ресурсу, в большинстве случаев следует реализовать требование безопасности относительно наличия у вызывающих объектов этого класса соответствующего разрешения.</span><span class="sxs-lookup"><span data-stu-id="f993b-137">If you design a class library and a class accesses a protected resource, you should, in most cases, make a security demand requiring that the callers of the class have the appropriate permission.</span></span> <span data-ttu-id="f993b-138">Если класс выполняет операцию, для которой у большинства вызывающих не будет разрешения, и вы готовы принять ответственность за предоставление этим вызывающим объектам вызывать ваш код, можно утвердить разрешение, вызвав **Assert** метода для объекта разрешения, представляющий операцию выполняет код.</span><span class="sxs-lookup"><span data-stu-id="f993b-138">If the class then performs an operation for which you know most of its callers will not have permission, and if you are willing to take the responsibility for letting these callers call your code, you can assert the permission by calling the **Assert** method on a permission object that represents the operation the code is performing.</span></span> <span data-ttu-id="f993b-139">С помощью **Assert** таким образом, вы позволяете вызывающим объектам, которые обычно не удалось вызвать ваш код.</span><span class="sxs-lookup"><span data-stu-id="f993b-139">Using **Assert** in this way lets callers that normally could not do so call your code.</span></span> <span data-ttu-id="f993b-140">Таким образом, если вы утверждаете разрешение, следует обязательно заранее выполнить соответствующие проверки безопасности, чтобы предотвратить неправильное использование вашего компонента.</span><span class="sxs-lookup"><span data-stu-id="f993b-140">Therefore, if you assert a permission, you should be sure to perform appropriate security checks beforehand to prevent your component from being misused.</span></span>  
  
 <span data-ttu-id="f993b-141">Например, предположим, что ваш в высшей степени доверенный класс библиотеки содержит метод, удаляющий файлы.</span><span class="sxs-lookup"><span data-stu-id="f993b-141">For example, suppose your highly trusted library class has a method that deletes files.</span></span> <span data-ttu-id="f993b-142">Он обращается к файлу путем вызова неуправляемой функции Win32.</span><span class="sxs-lookup"><span data-stu-id="f993b-142">It accesses the file by calling an unmanaged Win32 function.</span></span> <span data-ttu-id="f993b-143">Вызывающий объект вызывает кода **удалить** метод, передавая имя файла для удаления, C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="f993b-143">A caller invokes your code's **Delete** method, passing in the name of the file to be deleted, C:\Test.txt.</span></span> <span data-ttu-id="f993b-144">В рамках **удалить** метод, код создает <xref:System.Security.Permissions.FileIOPermission> объект, представляющий доступ на запись к C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="f993b-144">Within the **Delete** method, your code creates a <xref:System.Security.Permissions.FileIOPermission> object representing write access to C:\Test.txt.</span></span> <span data-ttu-id="f993b-145">(Для удаления файла требуется доступ на запись.) Код запускает принудительную проверку безопасности путем вызова **FileIOPermission** объекта **запросу** метод.</span><span class="sxs-lookup"><span data-stu-id="f993b-145">(Write access is required to delete a file.) Your code then invokes an imperative security check by calling the **FileIOPermission** object's **Demand** method.</span></span> <span data-ttu-id="f993b-146">Если один из вызывающих объектов в стеке вызовов не имеет этого разрешения, возникает исключение <xref:System.Security.SecurityException>.</span><span class="sxs-lookup"><span data-stu-id="f993b-146">If one of the callers in the call stack does not have this permission, a <xref:System.Security.SecurityException> is thrown.</span></span> <span data-ttu-id="f993b-147">Если исключение не выдается, вы можете быть уверены в том, что все вызывающие объекты имеют право доступа к C:\Test.txt.</span><span class="sxs-lookup"><span data-stu-id="f993b-147">If no exception is thrown, you know that all callers have the right to access C:\Test.txt.</span></span> <span data-ttu-id="f993b-148">Так как вы считаете, что большинство вызывающих объектов не будет разрешения на доступ к неуправляемому коду, код создает <xref:System.Security.Permissions.SecurityPermission> объект, представляющий право вызова неуправляемого кода и вызывает объект **Assert** метод.</span><span class="sxs-lookup"><span data-stu-id="f993b-148">Because you believe that most of your callers will not have permission to access unmanaged code, your code then creates a <xref:System.Security.Permissions.SecurityPermission> object that represents the right to call unmanaged code and calls the object's **Assert** method.</span></span> <span data-ttu-id="f993b-149">Наконец он вызывает неуправляемую функцию Win32 для удаления файла C:\Text.txt и возвращает управление вызывающему объекту.</span><span class="sxs-lookup"><span data-stu-id="f993b-149">Finally, it calls the unmanaged Win32 function to delete C:\Text.txt and returns control to the caller.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="f993b-150">Необходимо убедиться, что код не использует утверждения в ситуациях, когда ваш код может использоваться другим кодом для доступа к ресурсу, защищенному утверждаемым вами разрешением.</span><span class="sxs-lookup"><span data-stu-id="f993b-150">You must be sure that your code does not use assertions in situations where your code can be used by other code to access a resource that is protected by the permission you are asserting.</span></span> <span data-ttu-id="f993b-151">Например, в коде, который записывает в файл, имя которого указывается вызывающим объектом как параметр, не следует утверждать **FileIOPermission** на запись в файлы, так как ваш код будет открыт для неправильного использования третьей стороной.</span><span class="sxs-lookup"><span data-stu-id="f993b-151">For example, in code that writes to a file whose name is specified by the caller as a parameter, you would not assert the **FileIOPermission** for writing to files because your code would be open to misuse by a third party.</span></span>  
  
 <span data-ttu-id="f993b-152">При использовании принудительного синтаксиса безопасности вызов **Assert** метод для нескольких разрешений в одном методе приводит к возникновению исключения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f993b-152">When you use the imperative security syntax, calling the **Assert** method on multiple permissions in the same method causes a security exception to be thrown.</span></span> <span data-ttu-id="f993b-153">Вместо этого следует создать **PermissionSet** , передать ему отдельные разрешения, которые вы хотите вызвать, а затем вызвать **Assert** метод **PermissionSet** объект.</span><span class="sxs-lookup"><span data-stu-id="f993b-153">Instead, you should create a **PermissionSet** object, pass it the individual permissions you want to invoke, and then call the **Assert** method on the **PermissionSet** object.</span></span> <span data-ttu-id="f993b-154">Можно вызвать **Assert** более чем один раз при использовании декларативного синтаксиса безопасности метод.</span><span class="sxs-lookup"><span data-stu-id="f993b-154">You can call the **Assert** method more than once when you use the declarative security syntax.</span></span>  
  
 <span data-ttu-id="f993b-155">В следующем примере показано декларативный синтаксис для переопределения проверок безопасности с помощью **Assert** метод.</span><span class="sxs-lookup"><span data-stu-id="f993b-155">The following example shows declarative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="f993b-156">Обратите внимание, что **FileIOPermissionAttribute** синтаксис принимает два значения: <xref:System.Security.Permissions.SecurityAction> перечисления и расположение файла или каталога, к которому предоставляется разрешение.</span><span class="sxs-lookup"><span data-stu-id="f993b-156">Notice that the **FileIOPermissionAttribute** syntax takes two values: a <xref:System.Security.Permissions.SecurityAction> enumeration and the location of the file or directory to which permission is to be granted.</span></span> <span data-ttu-id="f993b-157">Вызов **Assert** требования для доступа к `C:\Log.txt` для успешного выполнения, несмотря на то, что вызывающие объекты не проверяются на разрешение доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="f993b-157">The call to **Assert** causes demands for access to `C:\Log.txt` to succeed, even though callers are not checked for permission to access the file.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
  
      End Sub  
  
     <FileIOPermission(SecurityAction.Assert, All := "C:\Log.txt")> Public Sub   
      MakeLog()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now) '  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      [FileIOPermission(SecurityAction.Assert, All = @"C:\Log.txt")]  
      public void MakeLog()  
      {     
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}   
```  
  
 <span data-ttu-id="f993b-158">В следующих фрагментах кода показан принудительный синтаксис для переопределения проверок безопасности с помощью **Assert** метод.</span><span class="sxs-lookup"><span data-stu-id="f993b-158">The following code fragments show imperative syntax for overriding security checks using the **Assert** method.</span></span> <span data-ttu-id="f993b-159">В этом примере экземпляр **FileIOPermission** объявлен объект.</span><span class="sxs-lookup"><span data-stu-id="f993b-159">In this example, an instance of the **FileIOPermission** object is declared.</span></span> <span data-ttu-id="f993b-160">Его конструктору передается **FileIOPermissionAccess.AllAccess** для определения типа разрешенного доступа, а затем строка, описывающая расположение файла.</span><span class="sxs-lookup"><span data-stu-id="f993b-160">Its constructor is passed **FileIOPermissionAccess.AllAccess** to define the type of access allowed, followed by a string describing the file's location.</span></span> <span data-ttu-id="f993b-161">Один раз **FileIOPermission** определения объектов, необходимо вызвать его **Assert** метод для переопределения проверки безопасности.</span><span class="sxs-lookup"><span data-stu-id="f993b-161">Once the **FileIOPermission** object is defined, you only need to call its **Assert** method to override the security check.</span></span>  
  
```vb  
Option Explicit  
Option Strict  
Imports System  
Imports System.IO  
Imports System.Security.Permissions  
Namespace LogUtil  
   Public Class Log  
      Public Sub New()  
      End Sub 'New  
  
      Public Sub MakeLog()  
         Dim FilePermission As New FileIOPermission(FileIOPermissionAccess.AllAccess, "C:\Log.txt")  
         FilePermission.Assert()  
         Dim TextStream As New StreamWriter("C:\Log.txt")  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now)  
         TextStream.Close()  
      End Sub  
   End Class  
End Namespace  
```  
  
```csharp  
namespace LogUtil  
{  
   using System;  
   using System.IO;  
   using System.Security.Permissions;  
  
   public class Log  
   {  
      public Log()  
      {      
      }     
      public void MakeLog()  
      {  
         FileIOPermission FilePermission = new FileIOPermission(FileIOPermissionAccess.AllAccess,@"C:\Log.txt");   
         FilePermission.Assert();  
         StreamWriter TextStream = new StreamWriter(@"C:\Log.txt");  
         TextStream.WriteLine("This  Log was created on {0}", DateTime.Now);  
         TextStream.Close();  
      }  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f993b-162">См. также</span><span class="sxs-lookup"><span data-stu-id="f993b-162">See also</span></span>

- <xref:System.Security.PermissionSet>
- <xref:System.Security.Permissions.SecurityPermission>
- <xref:System.Security.Permissions.FileIOPermission>
- <xref:System.Security.Permissions.SecurityAction>
- [<span data-ttu-id="f993b-163">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f993b-163">Attributes</span></span>](../../../docs/standard/attributes/index.md)
- [<span data-ttu-id="f993b-164">Управление доступом для кода</span><span class="sxs-lookup"><span data-stu-id="f993b-164">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
