---
title: Практическое руководство. Создание раздела реестра и задание его значения
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 459c4b3f971009ee4b6b669c55bc058db0826595
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74349204"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="cadd2-102">Практическое руководство. Создание раздела реестра и задание его значения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cadd2-102">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>

<span data-ttu-id="cadd2-103">Метод `CreateSubKey` объекта `My.Computer.Registry` можно использовать для создания раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="cadd2-103">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>

## <a name="procedure"></a><span data-ttu-id="cadd2-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="cadd2-104">Procedure</span></span>

### <a name="to-create-a-registry-key"></a><span data-ttu-id="cadd2-105">Создание раздела реестра</span><span class="sxs-lookup"><span data-stu-id="cadd2-105">To create a registry key</span></span>

- <span data-ttu-id="cadd2-106">Используйте метод `CreateSubKey`, задав куст, в который нужно поместить раздел, а также имя раздела.</span><span class="sxs-lookup"><span data-stu-id="cadd2-106">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="cadd2-107">Параметр `Subkey` нечувствителен к регистру.</span><span class="sxs-lookup"><span data-stu-id="cadd2-107">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="cadd2-108">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="cadd2-108">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="cadd2-109">Создание раздела реестра и задание его значения</span><span class="sxs-lookup"><span data-stu-id="cadd2-109">To create a registry key and set a value in it</span></span>

1. <span data-ttu-id="cadd2-110">Используйте метод `CreateSubkey`, задав куст, в который нужно поместить раздел, а также имя раздела.</span><span class="sxs-lookup"><span data-stu-id="cadd2-110">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="cadd2-111">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="cadd2-111">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. <span data-ttu-id="cadd2-112">Задайте значение с помощью метода `SetValue`.</span><span class="sxs-lookup"><span data-stu-id="cadd2-112">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="cadd2-113">В этом примере строке</span><span class="sxs-lookup"><span data-stu-id="cadd2-113">This example sets the string value.</span></span> <span data-ttu-id="cadd2-114">" MyTestKeyValue" присваивается значение "Это тестовое значение".</span><span class="sxs-lookup"><span data-stu-id="cadd2-114">"MyTestKeyValue" to "This is a test value".</span></span>

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a><span data-ttu-id="cadd2-115">Пример</span><span class="sxs-lookup"><span data-stu-id="cadd2-115">Example</span></span>

<span data-ttu-id="cadd2-116">В этом примере создается раздел реестра `MyTestKey` в HKEY_CURRENT_USER, а затем строке `MyTestKeyValue` задается значение `This is a test value`.</span><span class="sxs-lookup"><span data-stu-id="cadd2-116">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a><span data-ttu-id="cadd2-117">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="cadd2-117">Robust Programming</span></span>

<span data-ttu-id="cadd2-118">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="cadd2-118">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="cadd2-119">Для этого можно, например, открыть раздел HKEY_CURRENT_USER\Software текущего пользователя и создать раздел с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="cadd2-119">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="cadd2-120">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="cadd2-120">Then add the registry values to your company's key.</span></span>

<span data-ttu-id="cadd2-121">При чтении реестра из веб-приложения текущий пользователь зависит от проверки подлинности и олицетворения, реализованных в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="cadd2-121">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>

<span data-ttu-id="cadd2-122">Безопаснее записывать данные в папку пользователя (<xref:Microsoft.Win32.Registry.CurrentUser>), чем на локальный компьютер (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-122">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>

<span data-ttu-id="cadd2-123">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="cadd2-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="cadd2-124">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="cadd2-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="cadd2-125">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="cadd2-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="cadd2-126">Чтобы этого избежать, используйте метод <xref:Microsoft.Win32.RegistryKey.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="cadd2-126">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="cadd2-127">Он возвращает `Nothing`, если данный раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="cadd2-127">It returns `Nothing` if the key does not already exist.</span></span>

<span data-ttu-id="cadd2-128">Хранить секретные данные, например пароли, в реестре обычным текстом небезопасно, даже если раздел реестра защищен ACL (списком управления доступом).</span><span class="sxs-lookup"><span data-stu-id="cadd2-128">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>

<span data-ttu-id="cadd2-129">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="cadd2-129">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="cadd2-130">Имя ключа имеет значение `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-130">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="cadd2-131">У пользователя нет разрешения на создание разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-131">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="cadd2-132">Имя ключа превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-132">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="cadd2-133">Раздел является закрытым (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-133">The key is closed (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="cadd2-134">Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="cadd2-134">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="cadd2-135">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cadd2-135">.NET Framework Security</span></span>

<span data-ttu-id="cadd2-136">Для запуска этого процесса сборке нужен уровень привилегий, предоставляемый классом <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="cadd2-136">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="cadd2-137">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="cadd2-137">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="cadd2-138">Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.</span><span class="sxs-lookup"><span data-stu-id="cadd2-138">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="cadd2-139">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="cadd2-139">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="cadd2-140">Дополнительные сведения см. в разделе [Основы управления доступом для кода](../../../../framework/misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="cadd2-140">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cadd2-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cadd2-141">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [<span data-ttu-id="cadd2-142">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="cadd2-142">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="cadd2-143">Основы управления доступом для кода</span><span class="sxs-lookup"><span data-stu-id="cadd2-143">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
