---
title: Практическое руководство. Добавление ссылок на библиотеки типов
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- type libraries
- COM interop, importing type library
ms.assetid: f5cfa6ba-cc25-4017-82cd-ba7391859113
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4908653b650f05bd25a7893d104040802f34d7e4
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523819"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="dc14f-102">Практическое руководство. Добавление ссылок на библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="dc14f-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="dc14f-103">При добавлении ссылки на библиотеку типов Visual Studio генерирует сборку взаимодействия, в которой содержатся метаданные.</span><span class="sxs-lookup"><span data-stu-id="dc14f-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="dc14f-104">Если первичная сборка взаимодействия доступна, Visual Studio обращается к существующей сборке, прежде чем генерировать новую.</span><span class="sxs-lookup"><span data-stu-id="dc14f-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="dc14f-105">Добавление ссылки на библиотеку типов в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dc14f-105">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="dc14f-106">Если файл Windows Setup.exe не осуществит установку автоматически, установите DLL- или EXE-файл COM на компьютер.</span><span class="sxs-lookup"><span data-stu-id="dc14f-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="dc14f-107">Выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="dc14f-107">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="dc14f-108">В диспетчере ссылок выберите **COM**.</span><span class="sxs-lookup"><span data-stu-id="dc14f-108">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="dc14f-109">Выберите библиотеку типов из списка или найдите файл с расширением .TLB.</span><span class="sxs-lookup"><span data-stu-id="dc14f-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="dc14f-110">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="dc14f-110">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="dc14f-111">В обозревателе решений откройте контекстное меню добавленной ссылки и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="dc14f-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="dc14f-112">Убедитесь, что в окне **Свойства** свойству **Внедрить типы взаимодействия** присвоено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="dc14f-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="dc14f-113">Visual Studio внедрит информацию о типах COM в исполняемые файлы, устранив тем самым необходимость развертывать основные сборки взаимодействия в приложении.</span><span class="sxs-lookup"><span data-stu-id="dc14f-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dc14f-114">Пункты меню и параметры диалогового окна зависят от используемой версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dc14f-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="dc14f-115">Добавление ссылки на библиотеку типов для компиляции командной строки</span><span class="sxs-lookup"><span data-stu-id="dc14f-115">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="dc14f-116">Создайте сборку взаимодействия, как описывается в разделе [Практическое руководство. Создание сборок взаимодействия из библиотек типов](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="dc14f-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="dc14f-117">Используйте параметр компилятора [-LinkC# (параметры компилятора)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) с именем сборки взаимодействия, чтобы внедрить сведения о типах для COM-типов в исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="dc14f-117">Use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc14f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="dc14f-118">See also</span></span>

- [<span data-ttu-id="dc14f-119">Импорт библиотеки типов в виде сборки</span><span class="sxs-lookup"><span data-stu-id="dc14f-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="dc14f-120">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dc14f-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="dc14f-121">Пошаговое руководство. Внедрение типов из управляемых сборок в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="dc14f-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md) 
- [<span data-ttu-id="dc14f-122">-link (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="dc14f-122">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="dc14f-123">-Link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc14f-123">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
