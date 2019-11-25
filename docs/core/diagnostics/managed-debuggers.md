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
# <a name="net-core-managed-debuggers"></a>Управляемые отладчики в .NET Core

Отладчики позволяют приостанавливать программы или выполнять их пошагово. Вы сможете просмотреть текущее состояние процессов в приостановленной программе. Пошаговое выполнение важнейших разделов поможет изучить код программы и понять, почему он возвращает тот или иной результат.

Корпорация Майкрософт предоставляет отладчики для управляемого кода в **Visual Studio** и **Visual Studio Code**.

## <a name="visual-studio-managed-debugger"></a>Управляемый отладчик Visual Studio

**Visual Studio** — это интегрированная среда разработки с наиболее подробным из доступных отладчиков. Visual Studio отлично подходит для разработчиков, работающих с Windows.

- [Учебник по отладке приложений .NET Core на Windows с помощью Visual Studio](../tutorials/debugging-with-visual-studio.md)

Хотя Visual Studio является приложением Windows, его можно также использовать для удаленной отладки приложений Linux и macOS.

- [Отладка приложения .NET Core в Linux и OSX с помощью Visual Studio](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 Отладка приложений ASP.NET Core требует немного другого процесса.

- [Отладка приложений ASP.NET Core в Visual Studio](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a>Отладчик, управляемый Visual Studio Code

**Visual Studio Code** представляет собой небольшой кроссплатформенный редактор кода. Он использует ту же реализацию отладчика для .NET Core, что и Visual Studio, но с упрощенным пользовательским интерфейсом.

- [Учебник по отладке приложения .NET Core с помощью Visual Studio Code](../tutorials/with-visual-studio-code.md#debug)
- [Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging) (Отладка в Visual Studio Code)
