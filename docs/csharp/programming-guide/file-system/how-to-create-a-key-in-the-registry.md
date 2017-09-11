---
title: "Практическое руководство. Создание раздела в реестре (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.openlocfilehash: 96d34df3314494fc96ad8b55d7462b67dcc7bd72
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="d816c-102">Практическое руководство. Создание раздела в реестре (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="d816c-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="d816c-103">Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.</span><span class="sxs-lookup"><span data-stu-id="d816c-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="d816c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d816c-104">Example</span></span>  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d816c-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d816c-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="d816c-106">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="d816c-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="d816c-107">Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.</span><span class="sxs-lookup"><span data-stu-id="d816c-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="d816c-108">Замените параметр `Name` на имя значения, которое находится прямо в узле Names.</span><span class="sxs-lookup"><span data-stu-id="d816c-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d816c-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="d816c-109">Robust Programming</span></span>  
 <span data-ttu-id="d816c-110">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="d816c-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="d816c-111">Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="d816c-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="d816c-112">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="d816c-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="d816c-113">При следующих условиях может возникнуть исключение:</span><span class="sxs-lookup"><span data-stu-id="d816c-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="d816c-114">Пустое имя ключа.</span><span class="sxs-lookup"><span data-stu-id="d816c-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="d816c-115">У пользователя нет разрешения на создание разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="d816c-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="d816c-116">Имя ключа превышает ограничение в 255 символов.</span><span class="sxs-lookup"><span data-stu-id="d816c-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="d816c-117">Раздел является закрытым.</span><span class="sxs-lookup"><span data-stu-id="d816c-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="d816c-118">Раздел реестра доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="d816c-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d816c-119">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d816c-119">.NET Framework Security</span></span>  
 <span data-ttu-id="d816c-120">Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="d816c-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="d816c-121">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="d816c-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="d816c-122">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="d816c-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="d816c-123">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="d816c-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="d816c-124">Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="d816c-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="d816c-125">метод.</span><span class="sxs-lookup"><span data-stu-id="d816c-125">method.</span></span> <span data-ttu-id="d816c-126">Он возвращает значение NULL, если раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="d816c-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="d816c-127">Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="d816c-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d816c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d816c-128">See Also</span></span>  
 <span data-ttu-id="d816c-129"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d816c-129"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="d816c-130">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d816c-130">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d816c-131">[Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="d816c-131">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 [<span data-ttu-id="d816c-132">Чтение, запись и удаление данных реестра с помощью C#</span><span class="sxs-lookup"><span data-stu-id="d816c-132">Read, write and delete from the registry with C#</span></span>](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)

