---
title: "Практическое руководство. Чтение значения из раздела реестра в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 69b833777629cfd642ab75ac055b96b59c1da70b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="4a52e-102">Практическое руководство. Чтение значения из раздела реестра в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a52e-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="4a52e-103">Для чтения значений из реестра Windows можно использовать метод `GetValue` объекта `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="4a52e-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="4a52e-104">Если раздел (в данном случае "Software\MyApp") не существует, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="4a52e-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="4a52e-105">Если `ValueName` (в данном случае "Name") не существует, возвращается `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="4a52e-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="4a52e-106">Метод `GetValue` также можно использовать для определения наличия заданного значения в определенном разделе реестра.</span><span class="sxs-lookup"><span data-stu-id="4a52e-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="4a52e-107">Когда код считывает реестр из веб-приложения, текущий пользователь определяется путем проверки подлинности и олицетворения, реализованного в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="4a52e-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="4a52e-108">Чтение значения из раздела реестра</span><span class="sxs-lookup"><span data-stu-id="4a52e-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="4a52e-109">Для чтения значения из раздела реестра используйте метод `GetValue`, указав путь и имя.</span><span class="sxs-lookup"><span data-stu-id="4a52e-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="4a52e-110">В следующем примере считывается значение `Name` из раздела `HKEY_CURRENT_USER\Software\MyApp`, после чего оно отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="4a52e-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     <span data-ttu-id="4a52e-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4a52e-111">[!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]</span></span>  
  
 <span data-ttu-id="4a52e-112">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="4a52e-112">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="4a52e-113">В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Реестр**.</span><span class="sxs-lookup"><span data-stu-id="4a52e-113">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="4a52e-114">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="4a52e-114">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="4a52e-115">Определение наличия значения в разделе реестра</span><span class="sxs-lookup"><span data-stu-id="4a52e-115">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="4a52e-116">Чтобы получить значение, используйте метод `GetValue`.</span><span class="sxs-lookup"><span data-stu-id="4a52e-116">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="4a52e-117">В следующем коде проверяется наличие значения и возвращается сообщение, если значение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4a52e-117">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     <span data-ttu-id="4a52e-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4a52e-118">[!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4a52e-119">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4a52e-119">Robust Programming</span></span>  
 <span data-ttu-id="4a52e-120">Реестр содержит разделы верхнего уровня или корневые разделы, которые используются для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="4a52e-120">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="4a52e-121">Например, корневой раздел HKEY_LOCAL_MACHINE используется для хранения параметров уровня компьютера, используемых всеми пользователями, тогда как HKEY_CURRENT_USER используется для хранения данных для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a52e-121">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="4a52e-122">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="4a52e-122">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4a52e-123">Имя ключа имеет значение `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4a52e-123">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4a52e-124">У пользователя нет разрешений на создание разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4a52e-124">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="4a52e-125">Имя ключа превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4a52e-125">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4a52e-126">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4a52e-126">.NET Framework Security</span></span>  
 <span data-ttu-id="4a52e-127">Для запуска этого процесса сборке нужен уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="4a52e-127">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="4a52e-128">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="4a52e-128">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="4a52e-129">Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.</span><span class="sxs-lookup"><span data-stu-id="4a52e-129">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="4a52e-130">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4a52e-130">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="4a52e-131">Дополнительные сведения см. в разделе [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="4a52e-131">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a52e-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4a52e-132">See Also</span></span>  
 <span data-ttu-id="4a52e-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="4a52e-133"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="4a52e-134"><xref:Microsoft.Win32.RegistryHive></span><span class="sxs-lookup"><span data-stu-id="4a52e-134"><xref:Microsoft.Win32.RegistryHive></span></span>   
 [<span data-ttu-id="4a52e-135">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="4a52e-135">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

