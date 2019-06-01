---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 088ca6dd8973a626b1f028c638e60bf995af1e65
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66457322"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="d867a-102">Включение отладки с JIT-присоединением (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="d867a-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="d867a-103">Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.</span><span class="sxs-lookup"><span data-stu-id="d867a-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="d867a-104">Отладка с JIT-присоединением используется при следующих условиях сбоя:</span><span class="sxs-lookup"><span data-stu-id="d867a-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="d867a-105">Необработанные исключения (в машинном и управляемом коде).</span><span class="sxs-lookup"><span data-stu-id="d867a-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="d867a-106">Метод <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> или функция [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) (семейство ОС Windows 7).</span><span class="sxs-lookup"><span data-stu-id="d867a-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](https://go.microsoft.com/fwlink/?LinkId=182107) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="d867a-107">Неустранимые ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="d867a-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="d867a-108">Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:</span><span class="sxs-lookup"><span data-stu-id="d867a-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="d867a-109">Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d867a-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="d867a-110">Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d867a-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="d867a-111">Функция [DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) (Win32).</span><span class="sxs-lookup"><span data-stu-id="d867a-111">[DebugBreak](https://go.microsoft.com/fwlink/?LinkId=182106) function (Win32).</span></span>  
  
 <span data-ttu-id="d867a-112">В версиях платформы .NET Framework до [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] были представлены отдельные разделы реестра, определяющие поведение отладчиков машинного и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="d867a-112">Before the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="d867a-113">Начиная с .NET Framework 4, элемент управления является объединены в отдельного раздела реестра: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span><span class="sxs-lookup"><span data-stu-id="d867a-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="d867a-114">Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="d867a-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="d867a-115">Сведения о настройке раздела реестра, см. в разделе [Настройка автоматической отладки](https://go.microsoft.com/fwlink/?LinkId=181767).</span><span class="sxs-lookup"><span data-stu-id="d867a-115">For information about setting this registry key, see [Configuring Automatic Debugging](https://go.microsoft.com/fwlink/?LinkId=181767).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d867a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d867a-116">See also</span></span>

- [<span data-ttu-id="d867a-117">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="d867a-117">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
- [<span data-ttu-id="d867a-118">Упрощение отладки образов</span><span class="sxs-lookup"><span data-stu-id="d867a-118">Making an Image Easier to Debug</span></span>](../../../docs/framework/debug-trace-profile/making-an-image-easier-to-debug.md)
