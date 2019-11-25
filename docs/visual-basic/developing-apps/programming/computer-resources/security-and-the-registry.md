---
title: Безопасность и реестр
ms.date: 07/20/2015
helpviewer_keywords:
- security [Visual Basic], registry
- registry [Visual Basic], security issues
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
ms.openlocfilehash: 454180207d6432e80d87941d1f329f2a4ea7a801
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345487"
---
# <a name="security-and-the-registry-visual-basic"></a><span data-ttu-id="a3da0-102">Безопасность и реестр (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3da0-102">Security and the Registry (Visual Basic)</span></span>

<span data-ttu-id="a3da0-103">На этой странице обсуждается, как хранение данных в реестре сказывается на безопасности.</span><span class="sxs-lookup"><span data-stu-id="a3da0-103">This page discusses the security implications of storing data in the registry.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="a3da0-104">Разрешения</span><span class="sxs-lookup"><span data-stu-id="a3da0-104">Permissions</span></span>  

 <span data-ttu-id="a3da0-105">Хранить секретные данные, например пароли, в реестре обычным текстом небезопасно, даже если раздел реестра защищен ACL (списком управления доступом).</span><span class="sxs-lookup"><span data-stu-id="a3da0-105">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (access control lists).</span></span>  
  
 <span data-ttu-id="a3da0-106">Работа с реестром может привести к нарушению безопасности, допуская несанкционированный доступ к системным ресурсам или защищенной информации.</span><span class="sxs-lookup"><span data-stu-id="a3da0-106">Working with the registry may compromise security by allowing inappropriate access to system resources or protected information.</span></span> <span data-ttu-id="a3da0-107">Чтобы использовать эти свойства, необходимо иметь разрешения на чтение и запись в перечислении <xref:System.Security.Permissions.RegistryPermissionAccess>, которое управляет доступом к переменным реестра.</span><span class="sxs-lookup"><span data-stu-id="a3da0-107">To use these properties, you must have read and write permissions from the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration, which controls access to registry variables.</span></span> <span data-ttu-id="a3da0-108">Любой код, выполняющийся с полным доверием (в рамках политики безопасности по умолчанию это любой код, установленный на локальном жестком диске компьютера пользователя), имеет необходимые разрешения для доступа к реестру.</span><span class="sxs-lookup"><span data-stu-id="a3da0-108">Any code running with full trust (under the default security policy, this is any code installed on the user's local hard disk) has the necessary permissions to access the registry.</span></span> <span data-ttu-id="a3da0-109">Дополнительные сведения см. в разделе о классе <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="a3da0-109">For more information, see <xref:System.Security.Permissions.RegistryPermission> class.</span></span>  
  
 <span data-ttu-id="a3da0-110">Переменные реестра не следует хранить в областях памяти, к которым имеет доступ код без разрешений <xref:System.Security.Permissions.RegistryPermission>.</span><span class="sxs-lookup"><span data-stu-id="a3da0-110">Registry variables should not be stored in memory locations where code without <xref:System.Security.Permissions.RegistryPermission> can access them.</span></span> <span data-ttu-id="a3da0-111">Аналогичным образом, при предоставлении разрешений следует предоставлять минимальный уровень разрешений, необходимый для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="a3da0-111">Similarly, when granting permissions, grant the minimum privileges necessary to get the job done.</span></span>  
  
 <span data-ttu-id="a3da0-112">Значения разрешений на доступ к реестру определяются перечислением <xref:System.Security.Permissions.RegistryPermissionAccess>.</span><span class="sxs-lookup"><span data-stu-id="a3da0-112">Registry permission access values are defined by the <xref:System.Security.Permissions.RegistryPermissionAccess> enumeration.</span></span> <span data-ttu-id="a3da0-113">Его члены подробно рассмотрены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="a3da0-113">The following table details its members.</span></span>  
  
|<span data-ttu-id="a3da0-114">Значение</span><span class="sxs-lookup"><span data-stu-id="a3da0-114">Value</span></span>|<span data-ttu-id="a3da0-115">Доступ к переменным реестра</span><span class="sxs-lookup"><span data-stu-id="a3da0-115">Access to Registry Variables</span></span>|  
|-----------|----------------------------------|  
|`AllAccess`|<span data-ttu-id="a3da0-116">Создание, чтение и запись</span><span class="sxs-lookup"><span data-stu-id="a3da0-116">Create, read, and write</span></span>|  
|`Create`|<span data-ttu-id="a3da0-117">Создать</span><span class="sxs-lookup"><span data-stu-id="a3da0-117">Create</span></span>|  
|`NoAccess`|<span data-ttu-id="a3da0-118">Доступ отсутствует</span><span class="sxs-lookup"><span data-stu-id="a3da0-118">No access</span></span>|  
|`Read`|<span data-ttu-id="a3da0-119">Чтение</span><span class="sxs-lookup"><span data-stu-id="a3da0-119">Read</span></span>|  
|`Write`|<span data-ttu-id="a3da0-120">Write</span><span class="sxs-lookup"><span data-stu-id="a3da0-120">Write</span></span>|  
  
## <a name="checking-values-in-registry-keys"></a><span data-ttu-id="a3da0-121">Проверка значений в разделах реестра</span><span class="sxs-lookup"><span data-stu-id="a3da0-121">Checking Values in Registry Keys</span></span>  

 <span data-ttu-id="a3da0-122">Создавая значение реестра, необходимо решить, что делать, если это значение уже существует.</span><span class="sxs-lookup"><span data-stu-id="a3da0-122">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="a3da0-123">Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="a3da0-123">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="a3da0-124">Данные, добавленные в значение реестра, становятся доступными для другого процесса.</span><span class="sxs-lookup"><span data-stu-id="a3da0-124">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="a3da0-125">Чтобы этого избежать, используйте метод `GetValue`.</span><span class="sxs-lookup"><span data-stu-id="a3da0-125">To prevent this, use the `GetValue` method.</span></span> <span data-ttu-id="a3da0-126">Он возвращает `Nothing`, если данный раздел еще не существует.</span><span class="sxs-lookup"><span data-stu-id="a3da0-126">It returns `Nothing` if the key does not already exist.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="a3da0-127">При чтении реестра из веб-приложения идентификация текущего пользователя зависит от проверки подлинности и олицетворения, реализованных в веб-приложении.</span><span class="sxs-lookup"><span data-stu-id="a3da0-127">When reading the registry from a Web application, the identity of current user depends on the authentication and impersonation implemented in the Web application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3da0-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a3da0-128">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="a3da0-129">Чтение данных из реестра и запись в реестр</span><span class="sxs-lookup"><span data-stu-id="a3da0-129">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
