---
title: Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: e8bc4aa4ecd2bff2981b7d4faf1e270337f346e7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59346214"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="20f7c-102">Практическое руководство. Копирование и вставка элемента управления ElementHost во время разработки</span><span class="sxs-lookup"><span data-stu-id="20f7c-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="20f7c-103">Эта процедура показано, как скопировать элемент управления Windows Presentation Foundation (WPF) в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20f7c-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20f7c-104">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="20f7c-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="20f7c-105">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="20f7c-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="20f7c-106">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="20f7c-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="20f7c-107">Копирование и вставка элемента управления ElementHost во время разработки</span><span class="sxs-lookup"><span data-stu-id="20f7c-107">To copy and paste an ElementHost control at design time</span></span>  
  
1. <span data-ttu-id="20f7c-108">Добавить новый элемент управления WPF <xref:System.Windows.Controls.UserControl> в проект Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20f7c-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="20f7c-109">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="20f7c-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="20f7c-110">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового содержимого WPF в формах Windows Forms во время разработки](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="20f7c-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2. <span data-ttu-id="20f7c-111">В **свойства** окна, установите для параметра <xref:System.Windows.FrameworkElement.Width%2A> и <xref:System.Windows.FrameworkElement.Height%2A> свойства `UserControl1` для `200`.</span><span class="sxs-lookup"><span data-stu-id="20f7c-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3. <span data-ttu-id="20f7c-112">Задайте для свойства <xref:System.Windows.Controls.Control.Background%2A> значение `Blue`.</span><span class="sxs-lookup"><span data-stu-id="20f7c-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4. <span data-ttu-id="20f7c-113">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="20f7c-113">Build the project.</span></span>  
  
5. <span data-ttu-id="20f7c-114">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="20f7c-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6. <span data-ttu-id="20f7c-115">Из **элементов**, перетащите экземпляр `UserControl1` на форму.</span><span class="sxs-lookup"><span data-stu-id="20f7c-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="20f7c-116">Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="20f7c-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7. <span data-ttu-id="20f7c-117">Выбрав элемент управления `elementHost1`, нажмите клавиши CTRL+C, чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="20f7c-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8. <span data-ttu-id="20f7c-118">Нажмите клавиши CTRL + V, чтобы вставить скопированный элемент управления в форму.</span><span class="sxs-lookup"><span data-stu-id="20f7c-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="20f7c-119">Новый <xref:System.Windows.Forms.Integration.ElementHost> управления с именем `elementHost2` создается в форме.</span><span class="sxs-lookup"><span data-stu-id="20f7c-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f7c-120">См. также</span><span class="sxs-lookup"><span data-stu-id="20f7c-120">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="20f7c-121">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="20f7c-121">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="20f7c-122">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="20f7c-122">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="20f7c-123">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20f7c-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
