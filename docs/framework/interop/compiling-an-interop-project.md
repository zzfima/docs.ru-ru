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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6099764fb98604726da99ef71b9c82e9a931bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiling-an-interop-project"></a>Компиляция проекта, использующего взаимодействие
Проекты, использующие COM-взаимодействие, в которых содержатся ссылки на одну или несколько сборок с импортированными типами COM, компилируются так же, как и любые другие управляемые проекты. Ссылки на сборки взаимодействия можно использовать как в среде разработки (например, Visual Studio), так при использовании компилятора командной строки. В обоих случаях для корректной компиляции сборка взаимодействия должна находиться в одном каталоге с другими файлами проекта.  
  
 Ссылки на сборки взаимодействия можно использовать двумя способами:  
  
-   С помощью встроенных типов взаимодействия. Начиная с версий [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] и [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], можно дать указание компилятору внедрять сведения о типах из сборки взаимодействия в исполняемый файл. Это рекомендуемая методика.  
  
-   Развертывание сборок взаимодействия. Можно создать стандартную ссылку на сборку взаимодействия. В этом случае сборки взаимодействия должны быть развернуты вместе с приложением.  
  
 Различия между этими двумя способами более подробно описываются в разделе [Использование COM-типов в управляемом коде](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).  
  
 Внедрение типов взаимодействия в Visual Studio демонстрируется в разделах [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) и [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 Чтобы задать ссылку на сборку взаимодействия в компиляторе командной строки и внедрить сведения о типах в исполняемые файлы, задайте параметр компилятора [/link (параметры компилятора C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) и укажите имя сборки взаимодействия.  
  
> [!NOTE]
>  Приложения Visual C++ не поддерживают внедрение сведений о типах, однако могут взаимодействовать с приложениями и надстройками, в которых такая возможность присутствует.  
  
 Чтобы скомпилировать приложение, которое включает основную сборку взаимодействия при развертывании, задайте параметр компилятора **/reference** и укажите имя сборки взаимодействия.  
  
## <a name="see-also"></a>См. также  
 [Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)  
 [Независимость от языка и независимые от языка компоненты](../../standard/language-independence-and-language-independent-components.md)  
 [Использование типов COM в управляемом коде](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))  
 [Пошаговое руководство. Внедрение данных о типе из сборок для приложений Microsoft Office](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))  
 [Пошаговое руководство. Внедрение данных о типах из управляемых сборок](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)  
 [Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md)
