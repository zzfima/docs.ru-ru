---
title: Практическое руководство. Удаление раздела реестра в Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: fdb61fee8a790000c53b6c9a0188999bc0cb09ae
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840337"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="8e5b8-102">Практическое руководство. Удаление раздела реестра в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e5b8-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="8e5b8-103">Методы <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> и <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> можно использовать для удаления разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8e5b8-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="8e5b8-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="8e5b8-105">Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="8e5b8-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="8e5b8-106">Для удаления раздела реестра используйте метод `DeleteSubKey`.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="8e5b8-107">В этом примере удаляется раздел Software/TestApp в кусте CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="8e5b8-108">Можно изменить его в коде на подходящую строку или запросить значение для этого раздела у пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     [!code-vb[VbResourceTasks#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#19)]  
  
## <a name="robust-programming"></a><span data-ttu-id="8e5b8-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8e5b8-109">Robust Programming</span></span>  
 <span data-ttu-id="8e5b8-110">Метод `DeleteSubKey` возвратит пустую строку, если пара "раздел-значение" не существует.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-110">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="8e5b8-111">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="8e5b8-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8e5b8-112">Имя раздела — `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8e5b8-112">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8e5b8-113">У пользователя нет разрешений на удаление разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8e5b8-113">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8e5b8-114">Имя раздела превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8e5b8-114">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8e5b8-115">Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="8e5b8-115">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8e5b8-116">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8e5b8-116">.NET Framework Security</span></span>  
 <span data-ttu-id="8e5b8-117">Обращение к реестру невозможно, если не предоставлены достаточные разрешения времени выполнения (<xref:System.Security.Permissions.RegistryPermission>) или у пользователя нет надлежащих прав доступа (определенных списками управления доступом) для создания или записи параметров.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-117">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="8e5b8-118">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e5b8-118">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5b8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="8e5b8-119">See also</span></span>

- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>
- <xref:Microsoft.Win32.RegistryKey>
- [<span data-ttu-id="8e5b8-120">Безопасность и реестр</span><span class="sxs-lookup"><span data-stu-id="8e5b8-120">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
- [<span data-ttu-id="8e5b8-121">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="8e5b8-121">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
