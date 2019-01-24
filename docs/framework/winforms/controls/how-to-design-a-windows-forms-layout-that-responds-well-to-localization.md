---
title: Как выполнить Разработка макета формы Windows, с учетом будущей локализации
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
ms.openlocfilehash: 15f290f7d076eede7a8092d7295df810e4e51bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563526"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="761bd-102">Как выполнить Разработка макета формы Windows, с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="761bd-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>
<span data-ttu-id="761bd-103">Создание готовых для локализации форм значительно ускоряет разработку продуктов для международных рынков.</span><span class="sxs-lookup"><span data-stu-id="761bd-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="761bd-104">Элемент управления <xref:System.Windows.Forms.TableLayoutPanel> можно использовать для реализации макетов, которые поддерживают изменение размера элементов управления при изменении значений их свойств <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="761bd-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="761bd-105">Пример</span><span class="sxs-lookup"><span data-stu-id="761bd-105">Example</span></span>  
 <span data-ttu-id="761bd-106">Эта форма показывает, как создать макет, который пропорционально корректируется при отображении строковых значений на других языках.</span><span class="sxs-lookup"><span data-stu-id="761bd-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="761bd-107">Такой процесс перевода называется *локализацией*.</span><span class="sxs-lookup"><span data-stu-id="761bd-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="761bd-108">Подробнее об этом см. в разделе [Локализация](../../../../docs/standard/globalization-localization/localization.md).</span><span class="sxs-lookup"><span data-stu-id="761bd-108">For more information, see [Localization](../../../../docs/standard/globalization-localization/localization.md).</span></span>  
  
 <span data-ttu-id="761bd-109">В Visual Studio предусмотрена расширенная поддержка данной задачи.</span><span class="sxs-lookup"><span data-stu-id="761bd-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="761bd-110">См. также [Пошаговое руководство: Создание структуры, сохраняющей пропорции при локализации](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="761bd-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](https://msdn.microsoft.com/library/7k9fa71y\(v=vs.110\)).</span></span>  
  
 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]  
  
1.  [<span data-ttu-id="761bd-111">Практическое руководство. Выравнивание и Растягивание элемента управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="761bd-111">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)  
  
2.  <span data-ttu-id="761bd-112">[Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-112">[Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](https://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))</span></span>  
  
3.  [<span data-ttu-id="761bd-113">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="761bd-113">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)  
  
4.  [<span data-ttu-id="761bd-114">Практическое руководство. Изменение столбцов и строк в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="761bd-114">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)  
  
5.  <span data-ttu-id="761bd-115">[Пошаговое руководство: Выполнение типичных задач с помощью смарт-тегов в Windows Forms элементы управления](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-115">[Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls](https://msdn.microsoft.com/library/xhz359sc\(v=vs.110\))</span></span>  
  
6.  <span data-ttu-id="761bd-116">[Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-116">[Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel](https://msdn.microsoft.com/library/w4yc3e8c\(v=vs.110\))</span></span>  
  
7.  <span data-ttu-id="761bd-117">[Пошаговое руководство: Создание структуры Windows Forms элементов управления с помощью свойств Padding, Margins и свойство AutoSize](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-117">[Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](https://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))</span></span>  
  
8.  <span data-ttu-id="761bd-118">[Практическое руководство. Поддержки локализации в Windows Forms, с помощью функции AutoSize и элемента управления TableLayoutPanel](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-118">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](https://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))</span></span>  
  
9. <span data-ttu-id="761bd-119">[Пошаговое руководство: Создание переменного размера Windows формы для ввода данных](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="761bd-119">[Walkthrough: Creating a Resizable Windows Form for Data Entry](https://msdn.microsoft.com/library/991eahec\(v=vs.110\))</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="761bd-120">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="761bd-120">Compiling the Code</span></span>  
 <span data-ttu-id="761bd-121">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="761bd-121">This example requires:</span></span>  
  
-   <span data-ttu-id="761bd-122">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="761bd-122">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="761bd-123">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="761bd-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="761bd-124">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="761bd-124">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="761bd-125">Также см. раздел [Как Компиляция и выполнение примера кода завершения Windows Forms с помощью Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="761bd-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761bd-126">См. также</span><span class="sxs-lookup"><span data-stu-id="761bd-126">See also</span></span>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="761bd-127">Локализация</span><span class="sxs-lookup"><span data-stu-id="761bd-127">Localization</span></span>](../../../../docs/standard/globalization-localization/localization.md)
