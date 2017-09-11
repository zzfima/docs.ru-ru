---
title: "Практическое руководство. Удаление раздела реестра в Visual Basic"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
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
ms.openlocfilehash: 0fc37aff9f6a0ae3a7953377ebf95179d01bb693
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a><span data-ttu-id="8e6d8-102">Практическое руководство. Удаление раздела реестра в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8e6d8-102">How to: Delete a Registry Key in Visual Basic</span></span>
<span data-ttu-id="8e6d8-103">Методы <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> и <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> можно использовать для удаления разделов реестра.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-103">The <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> and <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> methods can be used to delete registry keys.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="8e6d8-104">Процедура</span><span class="sxs-lookup"><span data-stu-id="8e6d8-104">Procedure</span></span>  
  
#### <a name="to-delete-a-registry-key"></a><span data-ttu-id="8e6d8-105">Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="8e6d8-105">To delete a registry key</span></span>  
  
-   <span data-ttu-id="8e6d8-106">Для удаления раздела реестра используйте метод `DeleteSubKey`.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-106">Use the `DeleteSubKey` method to delete a registry key.</span></span> <span data-ttu-id="8e6d8-107">В этом примере удаляется раздел Software/TestApp в кусте CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-107">This example deletes the key Software/TestApp in the CurrentUser hive.</span></span> <span data-ttu-id="8e6d8-108">Можно изменить его в коде на подходящую строку или запросить значение для этого раздела у пользователя.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-108">You can change this in the code to the appropriate string, or have it rely on user-supplied information.</span></span>  
  
     <span data-ttu-id="8e6d8-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8e6d8-109">[!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8e6d8-110">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="8e6d8-110">Robust Programming</span></span>  
 <span data-ttu-id="8e6d8-111">Метод `DeleteSubKey` возвратит пустую строку, если пара "раздел-значение" не существует.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-111">The `DeleteSubKey` method returns an empty string if the key/value pair does not exist.</span></span>  
  
 <span data-ttu-id="8e6d8-112">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="8e6d8-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="8e6d8-113">Имя раздела — `Nothing` (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="8e6d8-113">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="8e6d8-114">У пользователя нет разрешений на удаление разделов реестра (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="8e6d8-114">The user does not have permissions to delete registry keys (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="8e6d8-115">Имя раздела превышает ограничение в 255 символов (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="8e6d8-115">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="8e6d8-116">Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="8e6d8-116">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="8e6d8-117">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8e6d8-117">.NET Framework Security</span></span>  
 <span data-ttu-id="8e6d8-118">Обращение к реестру невозможно, если не предоставлены достаточные разрешения времени выполнения (<xref:System.Security.Permissions.RegistryPermission>) или у пользователя нет надлежащих прав доступа (определенных списками управления доступом) для создания или записи параметров.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-118">Registry calls fail if either sufficient run-time permissions are not granted (<xref:System.Security.Permissions.RegistryPermission>) or if the user does not have the correct access (as determined by the ACLs) for creating or writing to settings.</span></span> <span data-ttu-id="8e6d8-119">Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.</span><span class="sxs-lookup"><span data-stu-id="8e6d8-119">For example, a local application that has the code access security permission might not have operating system permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e6d8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8e6d8-120">See Also</span></span>  
 <span data-ttu-id="8e6d8-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="8e6d8-121"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="8e6d8-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span><span class="sxs-lookup"><span data-stu-id="8e6d8-122"><xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A></span></span>   
 <span data-ttu-id="8e6d8-123"><xref:Microsoft.Win32.RegistryKey></span><span class="sxs-lookup"><span data-stu-id="8e6d8-123"><xref:Microsoft.Win32.RegistryKey></span></span>   
 <span data-ttu-id="8e6d8-124">[Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="8e6d8-124">[Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md) </span></span>  
 [<span data-ttu-id="8e6d8-125">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="8e6d8-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)

