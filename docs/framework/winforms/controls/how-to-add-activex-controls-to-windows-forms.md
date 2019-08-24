---
title: Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987058"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="36f73-102">Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="36f73-103">Хотя конструктор Windows Forms в Visual Studio оптимизированы для размещения элементов управления Windows Forms, можно также разместить элементы управления ActiveX на Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="36f73-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="36f73-104">При добавлении элементов управления ActiveX к ним применяются ограничения производительности Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="36f73-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="36f73-105">Перед добавлением элементов управления ActiveX в форму их необходимо добавить на панель элементов.</span><span class="sxs-lookup"><span data-stu-id="36f73-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="36f73-106">Дополнительные сведения см. в разделе [компоненты COM, диалоговое окно "Настройка панели элементов"](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="36f73-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="36f73-107">Добавление элемента управления ActiveX в форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="36f73-108">Чтобы добавить элемент управления ActiveX в форму Windows, дважды щелкните элемент управления на панели элементов.</span><span class="sxs-lookup"><span data-stu-id="36f73-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="36f73-109">Visual Studio добавляет все ссылки на элемент управления в проекте.</span><span class="sxs-lookup"><span data-stu-id="36f73-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="36f73-110">Дополнительные сведения о том, что следует помнить при использовании элементов управления ActiveX в Windows Forms, см. в разделе [рекомендации при размещении элемента управления ActiveX в форме Windows Forms](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="36f73-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="36f73-111">Windows Forms импортера элемента управления ActiveX (AxImp. exe) создает аргументы события другого типа, чем ожидалось при импорте библиотек динамической компоновки ActiveX.</span><span class="sxs-lookup"><span data-stu-id="36f73-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="36f73-112">Аргументы, созданные программой AxImp. exe, похожи на следующие: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, когда `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` ожидается.</span><span class="sxs-lookup"><span data-stu-id="36f73-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="36f73-113">Имейте в виду, что такая нерегулярность не мешает нормальному функционированию кода.</span><span class="sxs-lookup"><span data-stu-id="36f73-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="36f73-114">Дополнительные сведения см. в разделе [Windows Forms средство импорта элементов управления ActiveX (AxImp. exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span><span class="sxs-lookup"><span data-stu-id="36f73-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36f73-115">См. также</span><span class="sxs-lookup"><span data-stu-id="36f73-115">See also</span></span>

- [<span data-ttu-id="36f73-116">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="36f73-117">[Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="36f73-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="36f73-118">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="36f73-119">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="36f73-120">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="36f73-121">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36f73-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
