---
title: Управляемые отладчики (.NET Core)
description: Обзорные сведения об управляемых отладчиках в Visual Studio и Visual Studio Code.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.openlocfilehash: 3741011d22ab6c4240b7f88a9ab790ea61ecd0d2
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "72303650"
---
# <a name="net-core-managed-debuggers"></a><span data-ttu-id="5a741-103">Управляемые отладчики в .NET Core</span><span class="sxs-lookup"><span data-stu-id="5a741-103">.NET Core managed debuggers</span></span>

<span data-ttu-id="5a741-104">Отладчики позволяют приостанавливать программы или выполнять их пошагово.</span><span class="sxs-lookup"><span data-stu-id="5a741-104">Debuggers allow programs to be paused or executed step-by-step.</span></span> <span data-ttu-id="5a741-105">Вы сможете просмотреть текущее состояние процессов в приостановленной программе.</span><span class="sxs-lookup"><span data-stu-id="5a741-105">When paused, the current state of the process can be viewed.</span></span> <span data-ttu-id="5a741-106">Пошаговое выполнение важнейших разделов поможет изучить код программы и понять, почему он возвращает тот или иной результат.</span><span class="sxs-lookup"><span data-stu-id="5a741-106">By stepping through key sections, you gain understanding of your code and why it produces the result that it does.</span></span>

<span data-ttu-id="5a741-107">Корпорация Майкрософт предоставляет отладчики для управляемого кода в **Visual Studio** и **Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="5a741-107">Microsoft provides debuggers for managed code in **Visual Studio** and **Visual Studio Code**.</span></span>

## <a name="visual-studio-managed-debugger"></a><span data-ttu-id="5a741-108">Управляемый отладчик Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a741-108">Visual Studio managed debugger</span></span>

<span data-ttu-id="5a741-109">**Visual Studio** — это интегрированная среда разработки с наиболее подробным из доступных отладчиков.</span><span class="sxs-lookup"><span data-stu-id="5a741-109">**Visual Studio** is an integrated development environment with the most comprehensive debugger available.</span></span> <span data-ttu-id="5a741-110">Visual Studio отлично подходит для разработчиков, работающих с Windows.</span><span class="sxs-lookup"><span data-stu-id="5a741-110">Visual Studio is an excellent choice for developers working on Windows.</span></span>

- [<span data-ttu-id="5a741-111">Учебник по отладке приложений .NET Core на Windows с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a741-111">Tutorial - Debugging a .NET Core application on Windows with Visual Studio</span></span>](../tutorials/debugging-with-visual-studio.md)

<span data-ttu-id="5a741-112">Хотя Visual Studio является приложением Windows, его можно также использовать для удаленной отладки приложений Linux и macOS.</span><span class="sxs-lookup"><span data-stu-id="5a741-112">While Visual Studio is a Windows application, it can still be used to debug Linux and macOS apps remotely.</span></span>

- [<span data-ttu-id="5a741-113">Отладка приложения .NET Core в Linux и OSX с помощью Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a741-113">Debugging a .NET Core application on Linux/OSX with Visual Studio</span></span>](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 <span data-ttu-id="5a741-114">Отладка приложений ASP.NET Core требует немного другого процесса.</span><span class="sxs-lookup"><span data-stu-id="5a741-114">Debugging ASP.NET Core apps require slightly different instructions.</span></span>

- [<span data-ttu-id="5a741-115">Отладка приложений ASP.NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5a741-115">Debug ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a><span data-ttu-id="5a741-116">Отладчик, управляемый Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5a741-116">Visual Studio Code managed debugger</span></span>

<span data-ttu-id="5a741-117">**Visual Studio Code** представляет собой небольшой кроссплатформенный редактор кода.</span><span class="sxs-lookup"><span data-stu-id="5a741-117">**Visual Studio Code** is a lightweight cross-platform code editor.</span></span> <span data-ttu-id="5a741-118">Он использует ту же реализацию отладчика для .NET Core, что и Visual Studio, но с упрощенным пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="5a741-118">It uses the same .NET Core debugger implementation as Visual Studio, but with a simplified user interface.</span></span>

- [<span data-ttu-id="5a741-119">Учебник по отладке приложения .NET Core с помощью Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5a741-119">Tutorial - Debugging a .NET Core application with Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md#debug)
- <span data-ttu-id="5a741-120">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging) (Отладка в Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="5a741-120">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)</span></span>
