---
title: Руководство по программированию на C#. Как создать раздел в реестре
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 16974db950a3a460416cfb917147439707e1d007
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635448"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="04843-102">Руководство по программированию на C#. Создание раздела в реестре</span><span class="sxs-lookup"><span data-stu-id="04843-102">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="04843-103">Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.</span><span class="sxs-lookup"><span data-stu-id="04843-103">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="04843-104">Пример</span><span class="sxs-lookup"><span data-stu-id="04843-104">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="04843-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="04843-105">Compiling the Code</span></span>  
  
- <span data-ttu-id="04843-106">Скопируйте код и вставьте его в метод `Main` консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="04843-106">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="04843-107">Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.</span><span class="sxs-lookup"><span data-stu-id="04843-107">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="04843-108">Замените параметр `Name` на имя значения, которое находится прямо в узле Names.</span><span class="sxs-lookup"><span data-stu-id="04843-108">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="04843-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="04843-109">Robust Programming</span></span>  
 <span data-ttu-id="04843-110">Проверьте структуру реестра и найдите подходящее место для ключа.</span><span class="sxs-lookup"><span data-stu-id="04843-110">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="04843-111">Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании.</span><span class="sxs-lookup"><span data-stu-id="04843-111">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="04843-112">Затем добавьте в ключ компании значения реестра.</span><span class="sxs-lookup"><span data-stu-id="04843-112">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="04843-113">При следующих условиях может возникнуть исключение:</span><span class="sxs-lookup"><span data-stu-id="04843-113">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="04843-114">Пустое имя ключа.</span><span class="sxs-lookup"><span data-stu-id="04843-114">The name of the key is null.</span></span>  
  
- <span data-ttu-id="04843-115">У пользователя нет разрешения на создание разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="04843-115">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="04843-116">Имя ключа превышает ограничение в 255 символов.</span><span class="sxs-lookup"><span data-stu-id="04843-116">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="04843-117">Раздел является закрытым.</span><span class="sxs-lookup"><span data-stu-id="04843-117">The key is closed.</span></span>  
  
- <span data-ttu-id="04843-118">Раздел реестра доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="04843-118">The registry key is read-only.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="04843-119">Безопасность .NET Framework</span><span class="sxs-lookup"><span data-stu-id="04843-119">.NET Framework Security</span></span>  
 <span data-ttu-id="04843-120">Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).</span><span class="sxs-lookup"><span data-stu-id="04843-120">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="04843-121">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="04843-121">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="04843-122">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="04843-122">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="04843-123">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="04843-123">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="04843-124">Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="04843-124">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="04843-125">метод.</span><span class="sxs-lookup"><span data-stu-id="04843-125">method.</span></span> <span data-ttu-id="04843-126">Он возвращает значение NULL, если раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="04843-126">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="04843-127">Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).</span><span class="sxs-lookup"><span data-stu-id="04843-127">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04843-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="04843-128">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="04843-129">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="04843-129">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04843-130">Файловая система и реестр (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="04843-130">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="04843-131">Чтение, запись и удаление данных реестра с помощью C#</span><span class="sxs-lookup"><span data-stu-id="04843-131">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
