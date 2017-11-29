---
title: "Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d44358d3f76f50a06ede5e7d720f4f48d80893de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="0f1fe-102">Практическое руководство. Приостановка выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f1fe-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="0f1fe-103">В этом примере используется <xref:System.ServiceProcess.ServiceController> компонента, чтобы приостановить службу IIS Admin на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f1fe-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0f1fe-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="0f1fe-105">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="0f1fe-106">В средстве выбора фрагмента кода он находится в **операционная система Windows > службы Windows**.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="0f1fe-107">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="0f1fe-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f1fe-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0f1fe-108">Compiling the Code</span></span>  
 <span data-ttu-id="0f1fe-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="0f1fe-109">This example requires:</span></span>  
  
-   <span data-ttu-id="0f1fe-110">Ссылка проекта System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="0f1fe-111">Доступ к членам пространства имен <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="0f1fe-112">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="0f1fe-113">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="0f1fe-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0f1fe-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="0f1fe-114">Robust Programming</span></span>  
 <span data-ttu-id="0f1fe-115"><xref:System.ServiceProcess.ServiceController.MachineName%2A> Свойство <xref:System.ServiceProcess.ServiceController> класса — локальный компьютер по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="0f1fe-116">Чтобы обратиться к службам Windows на другом компьютере, измените <xref:System.ServiceProcess.ServiceController.MachineName%2A> на имя этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="0f1fe-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="0f1fe-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0f1fe-118">Служба не может быть приостановлена.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-118">The service cannot be paused.</span></span> <span data-ttu-id="0f1fe-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="0f1fe-119">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="0f1fe-120">Произошла ошибка при обращении к API-интерфейсу системы.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="0f1fe-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="0f1fe-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0f1fe-122">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0f1fe-122">.NET Framework Security</span></span>  
 <span data-ttu-id="0f1fe-123">Управление службами на компьютере может быть ограничен с помощью <xref:System.ServiceProcess.ServiceControllerPermissionAccess> для задания разрешений в <xref:System.ServiceProcess.ServiceControllerPermission>.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="0f1fe-124">Доступ к сведениям служб может быть ограничен с помощью <xref:System.Security.Permissions.PermissionState> для задания разрешений в <xref:System.Security.Permissions.SecurityPermission>.</span><span class="sxs-lookup"><span data-stu-id="0f1fe-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f1fe-125">См. также</span><span class="sxs-lookup"><span data-stu-id="0f1fe-125">See Also</span></span>  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [<span data-ttu-id="0f1fe-126">Как: возобновление выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f1fe-126">How to: Continue a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
