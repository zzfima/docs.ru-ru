---
title: Разработка макета, ориентированного на локализацию
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: 36ffd532b9f539107307144d25c8d9d5f8ba634a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743281"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="48821-102">Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="48821-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="48821-103">Создание готовых для локализации форм значительно ускоряет разработку продуктов для международных рынков.</span><span class="sxs-lookup"><span data-stu-id="48821-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="48821-104">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> можно использовать для реализации макетов, которые поддерживают изменение размера элементов управления при изменении значений их свойств <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="48821-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48821-105">Пример</span><span class="sxs-lookup"><span data-stu-id="48821-105">Example</span></span>  
 <span data-ttu-id="48821-106">Эта форма показывает, как создать макет, который пропорционально корректируется при отображении строковых значений на других языках.</span><span class="sxs-lookup"><span data-stu-id="48821-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="48821-107">Такой процесс перевода называется *локализацией*.</span><span class="sxs-lookup"><span data-stu-id="48821-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="48821-108">Подробнее об этом см. в разделе [Локализация](../../../standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="48821-108">For more information, see [Localization](../../../standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="48821-109">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="48821-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="48821-110">См. также раздел [Пошаговое руководство. Создание структуры, сохраняющей пропорции при локализации](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="48821-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
## <a name="additional-resources"></a><span data-ttu-id="48821-111">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="48821-111">Additional resources</span></span>

1. [<span data-ttu-id="48821-112">Практическое руководство. Выравнивание и растягивание элемента управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="48821-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2. [<span data-ttu-id="48821-113">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="48821-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  

3. [<span data-ttu-id="48821-114">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="48821-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4. [<span data-ttu-id="48821-115">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="48821-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5. [<span data-ttu-id="48821-116">Пошаговое руководство. Выполнение типичных задач с помощью смарт-тегов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="48821-116">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)  
  
6. [<span data-ttu-id="48821-117">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="48821-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  

7. [<span data-ttu-id="48821-118">Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize</span><span class="sxs-lookup"><span data-stu-id="48821-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)  
  
8. <span data-ttu-id="48821-119">[Практическое руководство. Обеспечение поддержки локализации в Windows Forms с помощью элементов управления AutoSize и TableLayoutPanel](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="48821-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>  
  
9. <span data-ttu-id="48821-120">[Пошаговое руководство. Создание в Windows Forms формы для ввода данных переменного размера](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="48821-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="48821-121">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="48821-121">Compiling the Code</span></span>  
 <span data-ttu-id="48821-122">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="48821-122">This example requires:</span></span>  
  
- <span data-ttu-id="48821-123">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="48821-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48821-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48821-124">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="48821-125">Локализация</span><span class="sxs-lookup"><span data-stu-id="48821-125">Localization</span></span>](../../../standard/globalization-localization/localization.md)
