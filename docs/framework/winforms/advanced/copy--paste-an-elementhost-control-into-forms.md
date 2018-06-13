---
title: Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
ms.openlocfilehash: 1cce981e4cb04ab6ed6ed41e0afac0121b242761
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520946"
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="4ca56-102">Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4ca56-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="4ca56-103">В этом пошаговом руководстве описывается, как скопировать элемент управления Windows Presentation Foundation (WPF) из одной формы Windows Forms в другую.</span><span class="sxs-lookup"><span data-stu-id="4ca56-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="4ca56-104">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4ca56-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4ca56-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="4ca56-105">Create the project.</span></span>  
  
-   <span data-ttu-id="4ca56-106">копирование элемента управления WPF.</span><span class="sxs-lookup"><span data-stu-id="4ca56-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ca56-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="4ca56-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4ca56-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="4ca56-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4ca56-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="4ca56-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ca56-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4ca56-110">Prerequisites</span></span>  
 <span data-ttu-id="4ca56-111">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="4ca56-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="4ca56-112">.</span><span class="sxs-lookup"><span data-stu-id="4ca56-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4ca56-113">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4ca56-113">Creating the Project</span></span>  
 <span data-ttu-id="4ca56-114">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ca56-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ca56-115">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4ca56-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4ca56-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4ca56-116">To create the project</span></span>  
  
-   <span data-ttu-id="4ca56-117">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="4ca56-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="4ca56-118">Копирование элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="4ca56-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="4ca56-119">После добавления в проект элемента управления WPF его можно скопировать в другие формы проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca56-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="4ca56-120">Копирование элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="4ca56-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="4ca56-121">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="4ca56-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="4ca56-122">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="4ca56-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="4ca56-123">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="4ca56-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="4ca56-124">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="4ca56-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="4ca56-125">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ca56-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="4ca56-126">Из **элементов**, перетащите экземпляр `UserControl1` в форму.</span><span class="sxs-lookup"><span data-stu-id="4ca56-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="4ca56-127">Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="4ca56-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="4ca56-128">Выбрав элемент управления `elementHost1`, нажмите клавиши CTRL+C, чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="4ca56-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="4ca56-129">Добавьте в проект новую форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4ca56-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="4ca56-130">Используйте имя по умолчанию для этого типа формы (`Form2`).</span><span class="sxs-lookup"><span data-stu-id="4ca56-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="4ca56-131">При открытой в конструкторе Windows Forms форме `Form2` нажмите клавиши CRTL+V, чтобы вставить в форму копию `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="4ca56-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="4ca56-132">Скопированный элемент управления также имеет имя `elementHost1`, так как это закрытое поле класса `Form2`.</span><span class="sxs-lookup"><span data-stu-id="4ca56-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="4ca56-133">Конфликта имен с `elementHost1` в классе `Form1` не возникает.</span><span class="sxs-lookup"><span data-stu-id="4ca56-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca56-134">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca56-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="4ca56-135">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="4ca56-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="4ca56-136">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="4ca56-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="4ca56-137">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="4ca56-137">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
