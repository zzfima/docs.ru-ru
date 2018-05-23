---
title: Чтение данных из реестра и запись в реестр (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Registry object, tasks
- registry [Visual Basic], writing to
- registry [Visual Basic], reading
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
ms.openlocfilehash: 6ce05b956ebf9a544eb8c95165b0f709c694f334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="reading-from-and-writing-to-the-registry-visual-basic"></a><span data-ttu-id="76807-102">Чтение данных из реестра и запись в реестр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="76807-102">Reading from and Writing to the Registry (Visual Basic)</span></span>
<span data-ttu-id="76807-103">В этом разделе описываются задачи и приводятся основные разделы, связанные с реестром.</span><span class="sxs-lookup"><span data-stu-id="76807-103">This topic describes task and conceptual topics that are associated with the registry.</span></span>  
  
 <span data-ttu-id="76807-104">При программировании в Visual Basic можно получить доступ к реестру с помощью функций, предоставляемых Visual Basic, или классов платформы .NET Framework для работы с реестром.</span><span class="sxs-lookup"><span data-stu-id="76807-104">When programming in Visual Basic, you can choose to access the registry by means of either the functions provided by Visual Basic or the registry classes of the .NET Framework.</span></span> <span data-ttu-id="76807-105">Реестр содержит данные, исходящие как от операционной системы, так и от приложений, установленных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="76807-105">The registry hosts information from the operating system as well as information from applications hosted on the machine.</span></span> <span data-ttu-id="76807-106">Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации.</span><span class="sxs-lookup"><span data-stu-id="76807-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76807-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="76807-107">In This Section</span></span>  
 [<span data-ttu-id="76807-108">Практическое руководство. Создание раздела реестра и задание его значения</span><span class="sxs-lookup"><span data-stu-id="76807-108">How to: Create a Registry Key and Set Its Value</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 <span data-ttu-id="76807-109">Описывает использование методов `CreateSubKey` и `SetValue` объекта `My.Computer.Registry` для создания раздела реестра и присвоения ему значения.</span><span class="sxs-lookup"><span data-stu-id="76807-109">Describes how to use the `CreateSubKey` and `SetValue` methods of the `My.Computer.Registry` object to create a registry key and set its value.</span></span>  
  
 [<span data-ttu-id="76807-110">Практическое руководство. Чтение значения из раздела реестра</span><span class="sxs-lookup"><span data-stu-id="76807-110">How to: Read a Value from a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 <span data-ttu-id="76807-111">Описывает использование метода `GetValue` объекта `My.Computer.Registry` для чтения значения из раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="76807-111">Describes how to use the `GetValue` method of the `My.Computer.Registry` object to read a value from a registry key.</span></span>  
  
 [<span data-ttu-id="76807-112">Практическое руководство. Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="76807-112">How to: Delete a Registry Key</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 <span data-ttu-id="76807-113">Описывает использование метода `DeleteSubKey` свойства `My.Computer.Registry.CurrentUser` для удаления раздела реестра.</span><span class="sxs-lookup"><span data-stu-id="76807-113">Describes how to use the `DeleteSubKey` method of the `My.Computer.Registry.CurrentUser` property to delete a registry key.</span></span>  
  
 [<span data-ttu-id="76807-114">Чтение реестра и запись в него с использованием пространства имен Microsoft.Win32</span><span class="sxs-lookup"><span data-stu-id="76807-114">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 <span data-ttu-id="76807-115">Описывает использование классов `Registry` и `RegistryKey` объекта [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] для доступа к реестру.</span><span class="sxs-lookup"><span data-stu-id="76807-115">Describes how to use the `Registry` and `RegistryKey` classes of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to access the registry.</span></span>  
  
 [<span data-ttu-id="76807-116">Безопасность и реестр</span><span class="sxs-lookup"><span data-stu-id="76807-116">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 <span data-ttu-id="76807-117">Описывает вопросы безопасности, связанные с реестром.</span><span class="sxs-lookup"><span data-stu-id="76807-117">Discusses security issues involving the registry.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="76807-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="76807-118">Related Sections</span></span>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <span data-ttu-id="76807-119">Список и описание членов объекта `My.Computer.Registry`.</span><span class="sxs-lookup"><span data-stu-id="76807-119">Lists and explains members of the `My.Computer.Registry` object.</span></span>  
  
 <xref:Microsoft.Win32.Registry>  
 <span data-ttu-id="76807-120">Обзор класса `Registry` со ссылками на отдельные разделы и члены.</span><span class="sxs-lookup"><span data-stu-id="76807-120">Presents an overview of the `Registry` class, along with links to individual keys and members.</span></span>
