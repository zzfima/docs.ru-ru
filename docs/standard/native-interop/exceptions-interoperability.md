---
title: Взаимодействие исключений
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794622"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="43daa-102">Работа с исключениями взаимодействия в неуправляемом коде</span><span class="sxs-lookup"><span data-stu-id="43daa-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="43daa-103">Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows.</span><span class="sxs-lookup"><span data-stu-id="43daa-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="43daa-104">Проблемы переносимости возникают на платформах, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="43daa-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="43daa-105">Поскольку интерфейс ABI для UNIX не имеет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений.</span><span class="sxs-lookup"><span data-stu-id="43daa-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="43daa-106">Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.</span><span class="sxs-lookup"><span data-stu-id="43daa-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="43daa-107">Поведение setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="43daa-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="43daa-108">Взаимодействие с функциями `setjmp` и `longjmp` C не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="43daa-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="43daa-109">Нельзя использовать `longjmp` для пропуска управляемых кадров.</span><span class="sxs-lookup"><span data-stu-id="43daa-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="43daa-110">Дополнительные сведения см. в [документации по longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="43daa-110">For more information, see [longjmp documentation](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="43daa-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="43daa-111">See also</span></span>

- [<span data-ttu-id="43daa-112">Исключения</span><span class="sxs-lookup"><span data-stu-id="43daa-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="43daa-113">Взаимодействие с собственными библиотеками</span><span class="sxs-lookup"><span data-stu-id="43daa-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
