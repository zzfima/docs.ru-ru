---
title: "Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
dev_langs:
- VB
helpviewer_keywords:
- registry keys, creating
- registry, adding values
- registry, adding keys
- registry keys, setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
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
ms.openlocfilehash: 106a98a1b15c37eb2cac05e1a681bf7dfed3543d
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="4f4c1-102">Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4f4c1-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>
<span data-ttu-id="4f4c1-103">Метод `CreateSubKey` объекта `My.Computer.Registry` можно использовать для создания раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="4f4c1-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="4f4c1-104">Procedure</span></span>  
  
#### <a name="to-create-a-registry-key"></a><span data-ttu-id="4f4c1-105">Создание раздела реестра</span><span class="sxs-lookup"><span data-stu-id="4f4c1-105">To create a registry key</span></span>  
  
-   <span data-ttu-id="4f4c1-106">Используйте метод `CreateSubKey`, задав куст, в который нужно поместить раздел, а также имя раздела.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="4f4c1-107">Параметр `Subkey` нечувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="4f4c1-108">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="4f4c1-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f4c1-109">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
#### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="4f4c1-110">Создание раздела реестра и задание его значения</span><span class="sxs-lookup"><span data-stu-id="4f4c1-110">To create a registry key and set a value in it</span></span>  
  
1.  <span data-ttu-id="4f4c1-111">Используйте метод `CreateSubkey`, задав куст, в который нужно поместить раздел, а также имя раздела.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-111">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="4f4c1-112">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-112">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>  
  
     <span data-ttu-id="4f4c1-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f4c1-113">[!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]</span></span>  
  
2.  <span data-ttu-id="4f4c1-114">Задайте значение с помощью метода `SetValue`.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-114">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="4f4c1-115">В этом примере строке</span><span class="sxs-lookup"><span data-stu-id="4f4c1-115">This example sets the string value.</span></span> <span data-ttu-id="4f4c1-116">" MyTestKeyValue" присваивается значение "Это тестовое значение".</span><span class="sxs-lookup"><span data-stu-id="4f4c1-116">"MyTestKeyValue" to "This is a test value".</span></span>  
  
     <span data-ttu-id="4f4c1-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f4c1-117">[!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f4c1-118">Пример</span><span class="sxs-lookup"><span data-stu-id="4f4c1-118">Example</span></span>  
 <span data-ttu-id="4f4c1-119">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER, а затем строке `This is a test value` задается значение `MyTestKeyValue`.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-119">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>  
  
 <span data-ttu-id="4f4c1-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4f4c1-120">[!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4f4c1-121">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4f4c1-121">Robust Programming</span></span>  
 <span data-ttu-id="4f4c1-122">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-122">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="4f4c1-123">Для этого можно, например, открыть раздел HKEY_CURRENT_USER\Software текущего пользователя и создать раздел с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-123">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="4f4c1-124">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-124">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="4f4c1-125">При чтении реестра из веб-приложения текущий пользователь зависит от проверки подлинности и олицетворения, реализованных в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-125">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
 <span data-ttu-id="4f4c1-126">Безопаснее записывать данные в папку пользователя (<xref:Microsoft.Win32.Registry.CurrentUser>), чем на локальный компьютер (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-126">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>  
  
 <span data-ttu-id="4f4c1-127">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-127">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="4f4c1-128">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-128">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="4f4c1-129">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-129">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="4f4c1-130">Чтобы этого избежать, используйте метод <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-130">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="4f4c1-131">Он возвращает `Nothing`, если данный раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-131">It returns `Nothing` if the key does not already exist.</span></span>  
  
 <span data-ttu-id="4f4c1-132">Хранить секретные данные, например пароли, в реестре обычным текстом небезопасно, даже если раздел реестра защищен ACL (списком управления доступом).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-132">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>  
  
 <span data-ttu-id="4f4c1-133">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="4f4c1-133">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="4f4c1-134">Имя раздела — `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-134">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="4f4c1-135">У пользователя нет разрешения на создание разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-135">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="4f4c1-136">Имя раздела превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-136">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4f4c1-137">Раздел является закрытым (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-137">The key is closed (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="4f4c1-138">Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-138">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="4f4c1-139">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4f4c1-139">.NET Framework Security</span></span>  
 <span data-ttu-id="4f4c1-140">Для запуска этого процесса сборке нужен уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-140">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="4f4c1-141">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-141">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="4f4c1-142">Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-142">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="4f4c1-143">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="4f4c1-143">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="4f4c1-144">Дополнительные сведения см. в разделе [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8).</span><span class="sxs-lookup"><span data-stu-id="4f4c1-144">For more information, see [Code Access Security Basics](https://msdn.microsoft.com/library/33tceax8).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f4c1-145">См. также</span><span class="sxs-lookup"><span data-stu-id="4f4c1-145">See Also</span></span>  
 <span data-ttu-id="4f4c1-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="4f4c1-146"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="4f4c1-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span><span class="sxs-lookup"><span data-stu-id="4f4c1-147"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A></span></span>   
 <span data-ttu-id="4f4c1-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="4f4c1-148"><xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A></span></span>   
 <span data-ttu-id="4f4c1-149">[Чтение данных из реестра и запись в реестр (Visual Basic)](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="4f4c1-149">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 [<span data-ttu-id="4f4c1-150">Основы управления доступом для кода</span><span class="sxs-lookup"><span data-stu-id="4f4c1-150">Code Access Security Basics</span></span>](https://msdn.microsoft.com/library/33tceax8)

