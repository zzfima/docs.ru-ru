---
title: Компиляция проекта, использующего взаимодействие
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: 32102910ae674a97e941e1346a1898585f503527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123675"
---
# <a name="compiling-an-interop-project"></a>Компиляция проекта, использующего взаимодействие

Проекты, использующие COM-взаимодействие, в которых содержатся ссылки на одну или несколько сборок с импортированными типами COM, компилируются так же, как и любые другие управляемые проекты. Ссылки на сборки взаимодействия можно использовать как в среде разработки (например, Visual Studio), так при использовании компилятора командной строки. В обоих случаях для корректной компиляции сборка взаимодействия должна находиться в одном каталоге с другими файлами проекта.

 Ссылки на сборки взаимодействия можно использовать двумя способами:

- Внедренные типы взаимодействия. Начиная с .NET Framework 4 и Visual Studio 2010, можно указать компилятору внедрять информацию о типах из сборки взаимодействия в исполняемый файл. Это рекомендуемая методика.

- Развертывание сборок взаимодействия. Можно создать стандартную ссылку на сборку взаимодействия. В этом случае сборки взаимодействия должны быть развернуты вместе с приложением.

 Различия между этими двумя способами более подробно описываются в разделе [Использование COM-типов в управляемом коде](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).

 Внедрение типов взаимодействия с помощью Visual Studio демонстрируется в разделе [Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio](../../standard/assembly/embed-types-visual-studio.md).

 Чтобы сослаться на сборку взаимодействия с помощью компилятора командной строки и внедрить сведения о типе в исполняемые файлы, используйте параметр [-C# Link (параметры компилятора)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) и укажите имя сборки взаимодействия.

> [!NOTE]
> Приложения Visual C++ не поддерживают внедрение сведений о типах, однако могут взаимодействовать с приложениями и надстройками, в которых такая возможность присутствует.

 Чтобы скомпилировать приложение, которое включает основную сборку взаимодействия при развертывании, задайте параметр компилятора **/reference** и укажите имя сборки взаимодействия.

## <a name="see-also"></a>См. также

- [Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)
- [Независимость от языка и независимые от языка компоненты](../../standard/language-independence-and-language-independent-components.md)
- [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) (Использование COM-типов в управляемом коде)
- [Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio](../../standard/assembly/embed-types-visual-studio.md)
- [Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md)
