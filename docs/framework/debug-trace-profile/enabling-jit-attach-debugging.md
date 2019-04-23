---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1696f9054d44a5f80a1f67cc38e315a8627d295
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078788"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="72269-102">Включение отладки с JIT-присоединением (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="72269-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="72269-103">Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.</span><span class="sxs-lookup"><span data-stu-id="72269-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="72269-104">Отладка с JIT-присоединением используется при следующих условиях сбоя:</span><span class="sxs-lookup"><span data-stu-id="72269-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
-   <span data-ttu-id="72269-105">Необработанные исключения (в машинном и управляемом коде).</span><span class="sxs-lookup"><span data-stu-id="72269-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
-   <span data-ttu-id="72269-106">Метод <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> или функция [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (семейство ОС Windows 7).</span><span class="sxs-lookup"><span data-stu-id="72269-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
-   <span data-ttu-id="72269-107">Неустранимые ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="72269-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="72269-108">Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:</span><span class="sxs-lookup"><span data-stu-id="72269-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
-   <span data-ttu-id="72269-109">Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72269-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="72269-110">Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="72269-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="72269-111">Функция [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).</span><span class="sxs-lookup"><span data-stu-id="72269-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="72269-112">В версиях платформы .NET Framework до [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] были представлены отдельные разделы реестра, определяющие поведение отладчиков машинного и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="72269-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="72269-113">Начиная с [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], элемент управления, объединяются в одном разделе реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="72269-113">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="72269-114">Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="72269-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="72269-115">Сведения о настройке раздела реестра, см. в разделе [Настройка автоматической отладки](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="72269-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72269-116">См. также</span><span class="sxs-lookup"><span data-stu-id="72269-116">See also</span></span>

- [<span data-ttu-id="72269-117">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="72269-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="72269-118">Упрощение отладки образов</span><span class="sxs-lookup"><span data-stu-id="72269-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
