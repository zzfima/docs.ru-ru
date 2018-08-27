---
title: Практическое руководство. Создание раздела в реестре (Visual C#)
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: f2b2cfcb09dc0c8c4d65b64f5de55c0b72746457
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752051"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a><span data-ttu-id="3f481-102">Практическое руководство. Создание раздела в реестре (Visual C#)</span><span class="sxs-lookup"><span data-stu-id="3f481-102">How to: Create a Key In the Registry (Visual C#)</span></span>
<span data-ttu-id="3f481-103">Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.</span><span class="sxs-lookup"><span data-stu-id="3f481-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f481-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3f481-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f481-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3f481-105">Compiling the Code</span></span>  
  
-   <span data-ttu-id="3f481-106">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="3f481-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
-   <span data-ttu-id="3f481-107">Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.</span><span class="sxs-lookup"><span data-stu-id="3f481-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
-   <span data-ttu-id="3f481-108">Замените параметр `Name` на имя значения, которое находится прямо в узле Names.</span><span class="sxs-lookup"><span data-stu-id="3f481-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3f481-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="3f481-109">Robust Programming</span></span>  
 <span data-ttu-id="3f481-110">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="3f481-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="3f481-111">Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="3f481-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="3f481-112">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="3f481-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="3f481-113">При следующих условиях может возникнуть исключение:</span><span class="sxs-lookup"><span data-stu-id="3f481-113">The following conditions might cause an exception:</span></span>  
  
-   <span data-ttu-id="3f481-114">Пустое имя ключа.</span><span class="sxs-lookup"><span data-stu-id="3f481-114">The name of the key is null.</span></span>  
  
-   <span data-ttu-id="3f481-115">У пользователя нет разрешения на создание разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="3f481-115">The user does not have permissions to create registry keys.</span></span>  
  
-   <span data-ttu-id="3f481-116">Имя ключа превышает ограничение в 255 символов.</span><span class="sxs-lookup"><span data-stu-id="3f481-116">The key name exceeds the 255-character limit.</span></span>  
  
-   <span data-ttu-id="3f481-117">Раздел является закрытым.</span><span class="sxs-lookup"><span data-stu-id="3f481-117">The key is closed.</span></span>  
  
-   <span data-ttu-id="3f481-118">Раздел реестра доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="3f481-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="3f481-119">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3f481-119">.NET Framework Security</span></span>  
 <span data-ttu-id="3f481-120">Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="3f481-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="3f481-121">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="3f481-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="3f481-122">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="3f481-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="3f481-123">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="3f481-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="3f481-124">Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="3f481-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="3f481-125">метод.</span><span class="sxs-lookup"><span data-stu-id="3f481-125">method.</span></span> <span data-ttu-id="3f481-126">Он возвращает значение NULL, если раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="3f481-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="3f481-127">Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="3f481-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f481-128">См. также</span><span class="sxs-lookup"><span data-stu-id="3f481-128">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="3f481-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="3f481-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3f481-130">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="3f481-130">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)  
 [<span data-ttu-id="3f481-131">Чтение, запись и удаление данных реестра с помощью C#</span><span class="sxs-lookup"><span data-stu-id="3f481-131">Read, write and delete from the registry with C#</span></span>](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
