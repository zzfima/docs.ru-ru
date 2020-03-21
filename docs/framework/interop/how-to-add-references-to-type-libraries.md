---
title: Практическое руководство. Добавление ссылок на библиотеки типов
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
ms.openlocfilehash: 1e82a499b77cc6d1d49eaf13e243201bbdc4c5fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181444"
---
# <a name="how-to-add-references-to-type-libraries"></a>Практическое руководство. Добавление ссылок на библиотеки типов
При добавлении ссылки на библиотеку типов Visual Studio генерирует сборку взаимодействия, в которой содержатся метаданные. Если первичная сборка взаимодействия доступна, Visual Studio обращается к существующей сборке, прежде чем генерировать новую.  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a>Добавление ссылки на библиотеку типов в Visual Studio  
  
1. Если файл Windows Setup.exe не осуществит установку автоматически, установите DLL- или EXE-файл COM на компьютер.  
  
2. Выберите **Проект**, **Добавить ссылку**.  
  
3. В диспетчере ссылок выберите **COM**.  
  
4. Выберите библиотеку типов из списка или найдите файл с расширением .TLB.  
  
5. Выберите **OK**.  
  
6. В обозревателе решений откройте контекстное меню добавленной ссылки и выберите **Свойства**.  
  
7. Убедитесь, что в окне **Свойства** свойству **Внедрить типы взаимодействия** присвоено значение **True**. Visual Studio внедрит информацию о типах COM в исполняемые файлы, устранив тем самым необходимость развертывать основные сборки взаимодействия в приложении.  
  
> [!NOTE]
> Пункты меню и параметры диалогового окна зависят от используемой версии Visual Studio.  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a>Добавление ссылки на библиотеку типов для компиляции командной строки  
  
1. Создайте сборку взаимодействия, как описывается в разделе [Практическое руководство. Создание сборок взаимодействия из библиотек типов](how-to-generate-interop-assemblies-from-type-libraries.md).  
  
2. Используйте [опцию компилятора -link (Параметры компилятора)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) с именем сборки interop для встраиваемого типа информации для типов COM в исполняемые.  
  
## <a name="see-also"></a>См. также раздел

- [Импорт библиотеки типов в виде сборки](importing-a-type-library-as-an-assembly.md)
- [Предоставление COM-компонентов платформе .NET Framework](exposing-com-components.md)
- [Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio](../../standard/assembly/embed-types-visual-studio.md)
- [-ссылка (Параметры компилятора)](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [-ссылка (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md)
