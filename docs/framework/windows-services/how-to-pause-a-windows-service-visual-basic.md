---
title: Как выполнить Приостановка выполнения службы Windows (Visual Basic)
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 8d378aba5ad09a38d24359fda8b50de072c58035
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612727"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a><span data-ttu-id="49349-102">Как выполнить Приостановка выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49349-102">How to: Pause a Windows Service (Visual Basic)</span></span>
<span data-ttu-id="49349-103">В этом примере для приостановки работы службы администрирования IIS на локальном компьютере используется компонент <xref:System.ServiceProcess.ServiceController>.</span><span class="sxs-lookup"><span data-stu-id="49349-103">This example uses the <xref:System.ServiceProcess.ServiceController> component to pause the IIS Admin service on the local computer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49349-104">Пример</span><span class="sxs-lookup"><span data-stu-id="49349-104">Example</span></span>  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 <span data-ttu-id="49349-105">Этот пример кода также доступен в качестве фрагмента кода IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="49349-105">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="49349-106">В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Службы Windows**.</span><span class="sxs-lookup"><span data-stu-id="49349-106">In the code snippet picker, it is located in **Windows Operating System > Windows Services**.</span></span> <span data-ttu-id="49349-107">Дополнительные сведения см. в статье [Фрагменты кода](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="49349-107">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49349-108">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="49349-108">Compiling the Code</span></span>  
 <span data-ttu-id="49349-109">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="49349-109">This example requires:</span></span>  
  
-   <span data-ttu-id="49349-110">Ссылка в проекте на System.serviceprocess.dll.</span><span class="sxs-lookup"><span data-stu-id="49349-110">A project reference to System.serviceprocess.dll.</span></span>  
  
-   <span data-ttu-id="49349-111">Доступ к членам пространства имен <xref:System.ServiceProcess>.</span><span class="sxs-lookup"><span data-stu-id="49349-111">Access to the members of the <xref:System.ServiceProcess> namespace.</span></span> <span data-ttu-id="49349-112">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="49349-112">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="49349-113">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="49349-113">For more information, see [Imports Statement (.NET Namespace and Type)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="49349-114">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="49349-114">Robust Programming</span></span>  
 <span data-ttu-id="49349-115">Свойство <xref:System.ServiceProcess.ServiceController.MachineName%2A> класса <xref:System.ServiceProcess.ServiceController> — это по умолчанию локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="49349-115">The <xref:System.ServiceProcess.ServiceController.MachineName%2A> property of the <xref:System.ServiceProcess.ServiceController> class is the local computer by default.</span></span> <span data-ttu-id="49349-116">Чтобы указать ссылку на службы Windows на другом компьютере, укажите в свойстве <xref:System.ServiceProcess.ServiceController.MachineName%2A> имя другого компьютера.</span><span class="sxs-lookup"><span data-stu-id="49349-116">To reference Windows services on another computer, change the <xref:System.ServiceProcess.ServiceController.MachineName%2A> property to the name of that computer.</span></span>  
  
 <span data-ttu-id="49349-117">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="49349-117">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="49349-118">Не удалось приостановить работу службы.</span><span class="sxs-lookup"><span data-stu-id="49349-118">The service cannot be paused.</span></span> <span data-ttu-id="49349-119">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="49349-119">(<xref:System.InvalidOperationException>)</span></span>  
  
-   <span data-ttu-id="49349-120">Произошла ошибка при обращении к API-интерфейсу системы.</span><span class="sxs-lookup"><span data-stu-id="49349-120">An error occurred when accessing a system API.</span></span> <span data-ttu-id="49349-121">(<xref:System.ComponentModel.Win32Exception>)</span><span class="sxs-lookup"><span data-stu-id="49349-121">(<xref:System.ComponentModel.Win32Exception>)</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="49349-122">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="49349-122">.NET Framework Security</span></span>  
 <span data-ttu-id="49349-123">Чтобы ограничить управление службами на компьютере, с помощью <xref:System.ServiceProcess.ServiceControllerPermissionAccess> настройте в <xref:System.ServiceProcess.ServiceControllerPermission> необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="49349-123">Control of services on the computer may be restricted by using the <xref:System.ServiceProcess.ServiceControllerPermissionAccess> to set permissions in the <xref:System.ServiceProcess.ServiceControllerPermission>.</span></span>  
  
 <span data-ttu-id="49349-124">Чтобы ограничить доступ к сведениям о службе, с помощью <xref:System.Security.Permissions.PermissionState> настройте в <xref:System.Security.Permissions.SecurityPermission> необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="49349-124">Access to service information may be restricted by using the <xref:System.Security.Permissions.PermissionState> to set permissions in the <xref:System.Security.Permissions.SecurityPermission>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49349-125">См. также</span><span class="sxs-lookup"><span data-stu-id="49349-125">See also</span></span>
- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [<span data-ttu-id="49349-126">Практическое руководство. Возобновление выполнения службы Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49349-126">How to: Continue a Windows Service (Visual Basic)</span></span>](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
