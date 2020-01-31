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
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Работа с исключениями взаимодействия в неуправляемом коде

Взаимодействие исключений неуправляемого кода поддерживается только на платформах Windows. Проблемы переносимости возникают на платформах, отличных от Windows. Поскольку интерфейс ABI для UNIX не имеет определения для обработки исключений, управляемый код не может понять, как работают механизмы исключений. Таким образом, исключения могут приводить к непредсказуемым поведению и сбоям.

## <a name="setjmplongjmp-behaviors"></a>Поведение setjmp/longjmp

Взаимодействие с функциями `setjmp` и `longjmp` C не поддерживается. Нельзя использовать `longjmp` для пропуска управляемых кадров.

Дополнительные сведения см. в [документации по longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>См. также:

- [Исключения](index.md)
- [Взаимодействие с собственными библиотеками](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
