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
ms.openlocfilehash: 4f0f254b7794ce1cd4c765bee70c78e3c60a14aa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946495"
---
# <a name="how-to-add-references-to-type-libraries"></a><span data-ttu-id="14d58-102">Практическое руководство. Добавление ссылок на библиотеки типов</span><span class="sxs-lookup"><span data-stu-id="14d58-102">How to: Add References to Type Libraries</span></span>
<span data-ttu-id="14d58-103">При добавлении ссылки на библиотеку типов Visual Studio генерирует сборку взаимодействия, в которой содержатся метаданные.</span><span class="sxs-lookup"><span data-stu-id="14d58-103">Visual Studio generates an interop assembly containing metadata when you add a reference to a type library.</span></span> <span data-ttu-id="14d58-104">Если первичная сборка взаимодействия доступна, Visual Studio обращается к существующей сборке, прежде чем генерировать новую.</span><span class="sxs-lookup"><span data-stu-id="14d58-104">If a primary interop assembly is available, Visual Studio uses the existing assembly before generating a new interop assembly.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-in-visual-studio"></a><span data-ttu-id="14d58-105">Добавление ссылки на библиотеку типов в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="14d58-105">To add a reference to a type library in Visual Studio</span></span>  
  
1. <span data-ttu-id="14d58-106">Если файл Windows Setup.exe не осуществит установку автоматически, установите DLL- или EXE-файл COM на компьютер.</span><span class="sxs-lookup"><span data-stu-id="14d58-106">Install the COM DLL or EXE file on your computer, unless a Windows Setup.exe file performs the installation for you.</span></span>  
  
2. <span data-ttu-id="14d58-107">Выберите **Проект**, **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="14d58-107">Choose **Project**, **Add Reference**.</span></span>  
  
3. <span data-ttu-id="14d58-108">В диспетчере ссылок выберите **COM**.</span><span class="sxs-lookup"><span data-stu-id="14d58-108">In the Reference Manager, choose **COM**.</span></span>  
  
4. <span data-ttu-id="14d58-109">Выберите библиотеку типов из списка или найдите файл с расширением .TLB.</span><span class="sxs-lookup"><span data-stu-id="14d58-109">Select the type library from the list, or browse for the .tlb file.</span></span>  
  
5. <span data-ttu-id="14d58-110">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="14d58-110">Choose **OK**.</span></span>  
  
6. <span data-ttu-id="14d58-111">В обозревателе решений откройте контекстное меню добавленной ссылки и выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="14d58-111">In Solution Explorer, open the shortcut menu for the reference you just added, and then choose **Properties**.</span></span>  
  
7. <span data-ttu-id="14d58-112">Убедитесь, что в окне **Свойства** свойству **Внедрить типы взаимодействия** присвоено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="14d58-112">In the **Properties** window, make sure that the **Embed Interop Types** property is set to **True**.</span></span> <span data-ttu-id="14d58-113">Visual Studio внедрит информацию о типах COM в исполняемые файлы, устранив тем самым необходимость развертывать основные сборки взаимодействия в приложении.</span><span class="sxs-lookup"><span data-stu-id="14d58-113">This causes Visual Studio to embed type information for COM types in your executables, eliminating the need to deploy primary interop assemblies with your app.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14d58-114">Пункты меню и параметры диалогового окна зависят от используемой версии Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="14d58-114">The menu and dialog box options may vary depending on the version of Visual Studio you're using.</span></span>  
  
### <a name="to-add-a-reference-to-a-type-library-for-command-line-compilation"></a><span data-ttu-id="14d58-115">Добавление ссылки на библиотеку типов для компиляции командной строки</span><span class="sxs-lookup"><span data-stu-id="14d58-115">To add a reference to a type library for command-line compilation</span></span>  
  
1. <span data-ttu-id="14d58-116">Сгенерируйте сборку взаимодействия, как описано в разделе [Практическое руководство. Создание сборок взаимодействия из библиотек типов](how-to-generate-interop-assemblies-from-type-libraries.md).</span><span class="sxs-lookup"><span data-stu-id="14d58-116">Generate an interop assembly as described in [How to: Generate Interop Assemblies from Type Libraries](how-to-generate-interop-assemblies-from-type-libraries.md).</span></span>  
  
2. <span data-ttu-id="14d58-117">Для внедрения информации о типах COM в исполняемые файлы используйте параметр компилятора [/link (параметры компилятора C#)](../../csharp/language-reference/compiler-options/link-compiler-option.md) или [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) с именем сборки взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="14d58-117">Use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler option with the interop assembly name to embed type information for COM types in your executables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14d58-118">См. также</span><span class="sxs-lookup"><span data-stu-id="14d58-118">See also</span></span>

- [<span data-ttu-id="14d58-119">Импорт библиотеки типов в виде сборки</span><span class="sxs-lookup"><span data-stu-id="14d58-119">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="14d58-120">Предоставление COM-компонентов платформе .NET Framework</span><span class="sxs-lookup"><span data-stu-id="14d58-120">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="14d58-121">Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio в C#</span><span class="sxs-lookup"><span data-stu-id="14d58-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>](../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md) 
- [<span data-ttu-id="14d58-122">Пошаговое руководство: Внедрение типов из управляемых сборок в Visual Studio (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14d58-122">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-vs.md)
- [<span data-ttu-id="14d58-123">/link (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="14d58-123">/link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="14d58-124">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14d58-124">/link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
