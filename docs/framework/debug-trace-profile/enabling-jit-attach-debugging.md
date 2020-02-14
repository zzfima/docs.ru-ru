---
title: Включение отладки с JIT-присоединением (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- JIT-attach debugging
- debugging [.NET Framework], JIT-attach debugging
ms.assetid: f91fc5f7-de5a-4f23-b6ac-f450e63c662e
ms.openlocfilehash: 7adf1316a36d781439d364746fa11795a7fe165a
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217536"
---
# <a name="enabling-jit-attach-debugging"></a><span data-ttu-id="e0ac2-102">Включение отладки с JIT-присоединением (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="e0ac2-102">Enabling JIT-Attach Debugging</span></span>
<span data-ttu-id="e0ac2-103">Отладка с JIT-присоединением предусматривает присоединение отладчика к процессу при возникновении ошибок. Также этот процесс может запускаться посредством определенных методов или функций.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-103">JIT-attach debugging is the phrase used to describe attaching a debugger to a process when you encounter errors, or it can be triggered by specific methods or functions.</span></span>  
  
 <span data-ttu-id="e0ac2-104">Отладка с JIT-присоединением используется при следующих условиях сбоя:</span><span class="sxs-lookup"><span data-stu-id="e0ac2-104">JIT-attach debugging is used under the following fault conditions:</span></span>  
  
- <span data-ttu-id="e0ac2-105">Необработанные исключения (в машинном и управляемом коде).</span><span class="sxs-lookup"><span data-stu-id="e0ac2-105">Unhandled exceptions (in both native and managed code).</span></span>  
  
- <span data-ttu-id="e0ac2-106">Метод <xref:System.Environment.FailFast%2A?displayProperty=nameWithType> или функция [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) (семейство ОС Windows 7).</span><span class="sxs-lookup"><span data-stu-id="e0ac2-106"><xref:System.Environment.FailFast%2A?displayProperty=nameWithType> method or [RaiseFailFastException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raisefailfastexception) function (Windows 7 family).</span></span>  
  
- <span data-ttu-id="e0ac2-107">Неустранимые ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-107">Runtime fatal errors.</span></span>  
  
 <span data-ttu-id="e0ac2-108">Отладка с JIT-присоединением также запускается посредством вызова следующих методов и функций:</span><span class="sxs-lookup"><span data-stu-id="e0ac2-108">JIT-attach debugging is also triggered by calls to the following methods and functions:</span></span>  
  
- <span data-ttu-id="e0ac2-109">Метод <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-109"><xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e0ac2-110">Метод <xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-110"><xref:System.Diagnostics.Debugger.Break%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e0ac2-111">Функция [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) (Win32).</span><span class="sxs-lookup"><span data-stu-id="e0ac2-111">[DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) function (Win32).</span></span>  
  
 <span data-ttu-id="e0ac2-112">Перед .NET Framework 4 в .NET Framework предоставлены отдельные разделы реестра для управления поведением отладчиков машинного и управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-112">Before the .NET Framework 4, the .NET Framework provided separate registry keys to control the behavior of native and managed debuggers.</span></span> <span data-ttu-id="e0ac2-113">Начиная с .NET Framework 4, управление консолидируется в одном разделе реестра: HKEY_LOCAL_MACHINE \Софтваре\микрософт\виндовс Нт\куррент Версион\аедебуг.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-113">Starting with the .NET Framework 4, control is consolidated under a single registry key: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\Current Version\AeDebug.</span></span> <span data-ttu-id="e0ac2-114">Значения этого раздела определяют, будет ли вызываться отладчик, а также будет ли в случае его вызова отображаться диалоговое окно для взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="e0ac2-114">The values you can set for that key determine whether a debugger is invoked, and, if so, whether it is invoked with a dialog box that requires user interaction.</span></span> <span data-ttu-id="e0ac2-115">Сведения об установке этого раздела реестра см. в разделе [Настройка автоматической отладки](/windows/win32/debug/configuring-automatic-debugging).</span><span class="sxs-lookup"><span data-stu-id="e0ac2-115">For information about setting this registry key, see [Configuring Automatic Debugging](/windows/win32/debug/configuring-automatic-debugging).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ac2-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="e0ac2-116">See also</span></span>

- [<span data-ttu-id="e0ac2-117">Отладка, трассировка и профилирование</span><span class="sxs-lookup"><span data-stu-id="e0ac2-117">Debugging, Tracing, and Profiling</span></span>](index.md)
- [<span data-ttu-id="e0ac2-118">Упрощение отладки образов</span><span class="sxs-lookup"><span data-stu-id="e0ac2-118">Making an Image Easier to Debug</span></span>](making-an-image-easier-to-debug.md)
