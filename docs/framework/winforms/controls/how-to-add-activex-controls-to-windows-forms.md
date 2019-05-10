---
title: Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210393"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="ea38d-102">Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="ea38d-103">Хотя в конструкторе Windows Forms в Visual Studio оптимизирована для размещения элементов управления Windows Forms, также можно поместить элементы управления ActiveX в формах Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ea38d-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="ea38d-104">Существуют ограничения производительности для Windows Forms, когда к ним добавляются элементы управления ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ea38d-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="ea38d-105">Чтобы добавить элементы управления ActiveX в форму, их необходимо добавить на панель элементов.</span><span class="sxs-lookup"><span data-stu-id="ea38d-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="ea38d-106">Дополнительные сведения см. в разделе [COM-компонентов, элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ea38d-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="ea38d-107">Добавление элемента управления ActiveX в форму Windows</span><span class="sxs-lookup"><span data-stu-id="ea38d-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="ea38d-108">Чтобы добавить элемент управления ActiveX в форму Windows, дважды щелкните элемент управления на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="ea38d-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="ea38d-109">Visual Studio добавляет все ссылки на элемент управления в проекте.</span><span class="sxs-lookup"><span data-stu-id="ea38d-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="ea38d-110">Дополнительные сведения о том, что следует учитывать при использовании элементов управления ActiveX в формах Windows Forms, см. в разделе [вопросы размещения элемента управления ActiveX в Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="ea38d-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ea38d-111">Импорта элемента управления ActiveX Windows Forms (AxImp.exe) создает аргументы события другого типа, чем требуется при импортировании библиотек динамической компоновки ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ea38d-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="ea38d-112">Аргументы, создаваемые по AxImp.exe, аналогичную следующей: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается.</span><span class="sxs-lookup"><span data-stu-id="ea38d-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="ea38d-113">Имейте в виду, что это нарушение правил не мешает код работает нормально.</span><span class="sxs-lookup"><span data-stu-id="ea38d-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="ea38d-114">Дополнительные сведения см. в разделе [Windows программа импорта элементов ActiveX форм (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="ea38d-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ea38d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ea38d-115">See also</span></span>

- [<span data-ttu-id="ea38d-116">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="ea38d-117">[Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ea38d-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="ea38d-118">Практическое руководство. Добавление элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="ea38d-119">Упорядочение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-119">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="ea38d-120">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="ea38d-121">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="ea38d-122">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ea38d-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
