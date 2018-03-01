---
title: "Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 73b16a5e5834f7279ae551d4e7efd26cc86c1d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a><span data-ttu-id="2d40c-102">Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d40c-102">How to: Continue a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="2d40c-103">В этом примере используется <xref:System.ServiceProcess.ServiceController> компонента, чтобы продолжить работу службы администрирования IIS на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="2d40c-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to continue the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d40c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2d40c-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 <span data-ttu-id="2d40c-105">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="2d40c-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="2d40c-106">В средстве выбора фрагмента кода он находится в **операционная система Windows > службы Windows**.</span><span class="sxs-lookup"><span data-stu-id="2d40c-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="2d40c-107">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="2d40c-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d40c-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2d40c-108">Compiling the Code</span></span>  
 <span data-ttu-id="2d40c-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2d40c-109">This example requires:</span></span>  
  
-   <span data-ttu-id="2d40c-110">Ссылка проекта System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="2d40c-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="2d40c-111">Доступ к членам пространства имен <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="2d40c-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="2d40c-112">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="2d40c-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="2d40c-113">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="2d40c-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2d40c-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="2d40c-114">Robust Programming</span></span>  
 <span data-ttu-id="2d40c-115"><xref:System.ServiceProcess.ServiceController.MachineName%2A> Свойство <xref:System.ServiceProcess.ServiceController> класса — локальный компьютер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2d40c-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="2d40c-116">Чтобы обратиться к службам Windows на другом компьютере, измените <xref:System.ServiceProcess.ServiceController.MachineName%2A> на имя этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="2d40c-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="2d40c-117">Не удается вызвать <xref:System.ServiceProcess.ServiceController.Continue%2A> метод службы, пока состояние контроллера службы — <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span><span class="sxs-lookup"><span data-stu-id="2d40c-117">You cannot call the <xref:System.ServiceProcess.ServiceController.Continue%2A> method on a service until the service controller status is <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.</span></span>  
  
 <span data-ttu-id="2d40c-118">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="2d40c-118">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="2d40c-119">Служба не может быть возобновлен.</span><span class="sxs-lookup"><span data-stu-id="2d40c-119">The service cannot be resumed.</span></span> <span data-ttu-id="2d40c-120">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="2d40c-120">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="2d40c-121">Произошла ошибка при обращении к API-интерфейсу системы.</span><span class="sxs-lookup"><span data-stu-id="2d40c-121">An error occurred when accessing a system API.</span></span> <span data-ttu-id="2d40c-122">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="2d40c-122">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="2d40c-123">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2d40c-123">.NET Framework Security</span></span>  
 <span data-ttu-id="2d40c-124">Управление службами на компьютере может быть ограничен с помощью <xref:System.ServiceProcess.ServiceControllerPermissionAccess> перечисления для задания разрешений в <xref:System.ServiceProcess.ServiceControllerPermission> класса.</span><span class="sxs-lookup"><span data-stu-id="2d40c-124">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> enumeration to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission> class.</span></span>  
  
 <span data-ttu-id="2d40c-125">Доступ к сведениям служб может быть ограничен с помощью <xref:System.Security.Permissions.PermissionState> перечисления для задания разрешений в <xref:System.Security.Permissions.SecurityPermission> класса.</span><span class="sxs-lookup"><span data-stu-id="2d40c-125">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> enumeration to set permissions in the <xref:System.Security.Permissions.SecurityPermission> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d40c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2d40c-126">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [<span data-ttu-id="2d40c-127">Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d40c-127">How to: Pause a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
