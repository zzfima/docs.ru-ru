---
title: Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e89510558274558e560bf810afe746e250ff26a4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459226"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="d25c2-102">Как копировать и вставить элемент управления ElementHost</span><span class="sxs-lookup"><span data-stu-id="d25c2-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="d25c2-103">В этой процедуре показано, как скопировать элемент управления Windows Presentation Foundation (WPF) в форму Windows в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d25c2-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="d25c2-104">В Visual Studio добавьте новый <xref:System.Windows.Controls.UserControl> WPF в проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d25c2-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="d25c2-105">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="d25c2-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="d25c2-106">Дополнительные сведения см. в разделе [Пошаговое руководство. Создание нового содержимого WPF на Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="d25c2-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="d25c2-107">В окне **Свойства** задайте для свойств <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> `UserControl1` значение **200**.</span><span class="sxs-lookup"><span data-stu-id="d25c2-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="d25c2-108">Присвойте свойству <xref:System.Windows.Controls.Control.Background%2A> значение **Blue**.</span><span class="sxs-lookup"><span data-stu-id="d25c2-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="d25c2-109">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="d25c2-109">Build the project.</span></span>

5. <span data-ttu-id="d25c2-110">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d25c2-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="d25c2-111">Из **панели элементов**перетащите экземпляр `UserControl1` на форму.</span><span class="sxs-lookup"><span data-stu-id="d25c2-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="d25c2-112">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="d25c2-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="d25c2-113">Выбрав `elementHost1`, нажмите клавиши **Ctrl**+**C** , чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="d25c2-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="d25c2-114">Нажмите клавиши **Ctrl**+**V** , чтобы вставить скопированный элемент управления на форму.</span><span class="sxs-lookup"><span data-stu-id="d25c2-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="d25c2-115">В форме создается новый элемент управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost2`.</span><span class="sxs-lookup"><span data-stu-id="d25c2-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d25c2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d25c2-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="d25c2-117">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="d25c2-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="d25c2-118">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="d25c2-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="d25c2-119">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d25c2-119">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
