---
title: "Практическое руководство. Чтение значения из раздела реестра в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- registry keys [Visual Basic], determining if a value exists in
- My.Computer.Registry object, examples
- registry [Visual Basic], determining if values exist
- registry keys [Visual Basic], reading from
- registry [Visual Basic], reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4aa939d7b2d89bd878705ac67f2b6f37838f6ea2
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a><span data-ttu-id="cbe29-102">Практическое руководство. Чтение значения из раздела реестра в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cbe29-102">How to: Read a Value from a Registry Key in Visual Basic</span></span>
<span data-ttu-id="cbe29-103">Для чтения значений из реестра Windows можно использовать метод `GetValue` объекта `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="cbe29-103">The `GetValue` method of the `My.Computer.Registry` object can be used to read values in the Windows registry.</span></span>  
  
 <span data-ttu-id="cbe29-104">Если раздел (в данном случае "Software\MyApp") не существует, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="cbe29-104">If the key, "Software\MyApp" in the following example, does not exist, an exception is thrown.</span></span> <span data-ttu-id="cbe29-105">Если `ValueName` (в данном случае "Name") не существует, возвращается `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="cbe29-105">If the `ValueName`,  "Name" in the following example, does not exist, `Nothing` is returned.</span></span>  
  
 <span data-ttu-id="cbe29-106">Метод `GetValue` также можно использовать для определения наличия заданного значения в определенном разделе реестра.</span><span class="sxs-lookup"><span data-stu-id="cbe29-106">The `GetValue` method can also be used to determine whether a given value exists in a specific registry key.</span></span>  
  
 <span data-ttu-id="cbe29-107">Когда код считывает реестр из веб-приложения, текущий пользователь определяется путем проверки подлинности и олицетворения, реализованного в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="cbe29-107">When code reads the registry from a Web application, the current user is determined by the authentication and impersonation that is implemented in the Web application.</span></span>  
  
### <a name="to-read-a-value-from-a-registry-key"></a><span data-ttu-id="cbe29-108">Чтение значения из раздела реестра</span><span class="sxs-lookup"><span data-stu-id="cbe29-108">To read a value from a registry key</span></span>  
  
-   <span data-ttu-id="cbe29-109">Для чтения значения из раздела реестра используйте метод `GetValue`, указав путь и имя.</span><span class="sxs-lookup"><span data-stu-id="cbe29-109">Use the `GetValue` method, specifying the path and name) to read a value from registry key.</span></span> <span data-ttu-id="cbe29-110">В следующем примере считывается значение `Name` из раздела `HKEY_CURRENT_USER\Software\MyApp`, после чего оно отображается в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="cbe29-110">The following example reads the value `Name` from `HKEY_CURRENT_USER\Software\MyApp` and displays it in a message box.</span></span>  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 <span data-ttu-id="cbe29-111">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="cbe29-111">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="cbe29-112">В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Реестр**.</span><span class="sxs-lookup"><span data-stu-id="cbe29-112">In the code snippet picker, it is located in **Windows Operating System > Registry**.</span></span> <span data-ttu-id="cbe29-113">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="cbe29-113">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a><span data-ttu-id="cbe29-114">Определение наличия значения в разделе реестра</span><span class="sxs-lookup"><span data-stu-id="cbe29-114">To determine whether a value exists in a registry key</span></span>  
  
-   <span data-ttu-id="cbe29-115">Чтобы получить значение, используйте метод `GetValue`.</span><span class="sxs-lookup"><span data-stu-id="cbe29-115">Use the `GetValue` method to retrieve the value.</span></span> <span data-ttu-id="cbe29-116">В следующем коде проверяется наличие значения и возвращается сообщение, если значение отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cbe29-116">The following code checks whether the value exists and returns a message if it does not.</span></span>  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a><span data-ttu-id="cbe29-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cbe29-117">Robust Programming</span></span>  
 <span data-ttu-id="cbe29-118">Реестр содержит разделы верхнего уровня или корневые разделы, которые используются для хранения данных.</span><span class="sxs-lookup"><span data-stu-id="cbe29-118">The registry holds top-level, or root, keys that are used to store data.</span></span> <span data-ttu-id="cbe29-119">Например, корневой раздел HKEY_LOCAL_MACHINE используется для хранения параметров уровня компьютера, используемых всеми пользователями, тогда как HKEY_CURRENT_USER используется для хранения данных для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="cbe29-119">For instance, the HKEY_LOCAL_MACHINE root key is used for storing machine-level settings used by all users, while HKEY_CURRENT_USER is used for storing data specific to an individual user.</span></span>  
  
 <span data-ttu-id="cbe29-120">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="cbe29-120">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="cbe29-121">Имя ключа имеет значение `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="cbe29-121">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="cbe29-122">У пользователя нет разрешений на создание разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="cbe29-122">The user does not have permissions to read from registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="cbe29-123">Имя ключа превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="cbe29-123">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cbe29-124">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cbe29-124">.NET Framework Security</span></span>  
 <span data-ttu-id="cbe29-125">Для запуска этого процесса сборке нужен уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="cbe29-125">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="cbe29-126">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="cbe29-126">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="cbe29-127">Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.</span><span class="sxs-lookup"><span data-stu-id="cbe29-127">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="cbe29-128">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cbe29-128">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="cbe29-129">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="cbe29-129">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe29-130">См. также</span><span class="sxs-lookup"><span data-stu-id="cbe29-130">See Also</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <xref:Microsoft.Win32.RegistryHive>  
 [<span data-ttu-id="cbe29-131">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="cbe29-131">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
