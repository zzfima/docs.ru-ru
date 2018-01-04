---
title: "Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 579bce312296d9799f9f7c739f740e2c9111ccff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="c1bd7-102">Пошаговое руководство. Копирование и вставка элемента интерфейса ElementHost в отдельную форму Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1bd7-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="c1bd7-103">В этом пошаговом руководстве описывается, как скопировать элемент управления Windows Presentation Foundation (WPF) из одной формы Windows Forms в другую.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="c1bd7-104">В руководстве выполняются следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c1bd7-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="c1bd7-105">создание проекта;</span><span class="sxs-lookup"><span data-stu-id="c1bd7-105">Create the project.</span></span>  
  
-   <span data-ttu-id="c1bd7-106">копирование элемента управления WPF.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1bd7-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c1bd7-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c1bd7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c1bd7-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c1bd7-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c1bd7-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c1bd7-110">Prerequisites</span></span>  
 <span data-ttu-id="c1bd7-111">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="c1bd7-112">.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="c1bd7-113">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c1bd7-113">Creating the Project</span></span>  
 <span data-ttu-id="c1bd7-114">Первым шагом является создание проекта Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1bd7-115">При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="c1bd7-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="c1bd7-116">To create the project</span></span>  
  
-   <span data-ttu-id="c1bd7-117">Создайте новый проект приложения Windows Forms в Visual Basic или Visual C# с именем `CopyElementHost`.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="c1bd7-118">Копирование элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="c1bd7-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="c1bd7-119">После добавления в проект элемента управления WPF его можно скопировать в другие формы проекта.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="c1bd7-120">Копирование элемента управления WPF</span><span class="sxs-lookup"><span data-stu-id="c1bd7-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="c1bd7-121">Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="c1bd7-122">Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`).</span><span class="sxs-lookup"><span data-stu-id="c1bd7-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="c1bd7-123">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание нового WPF содержимого в формах Windows Forms во время разработки](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="c1bd7-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="c1bd7-124">Выполните построение проекта.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="c1bd7-125">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="c1bd7-126">Из **элементов**, перетащите экземпляр `UserControl1` в форму.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="c1bd7-127">Экземпляр `UserControl1` разместится в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="c1bd7-128">Выбрав элемент управления `elementHost1`, нажмите клавиши CTRL+C, чтобы скопировать его в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="c1bd7-129">Добавьте в проект новую форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="c1bd7-130">Используйте имя по умолчанию для этого типа формы (`Form2`).</span><span class="sxs-lookup"><span data-stu-id="c1bd7-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="c1bd7-131">При открытой в конструкторе Windows Forms форме `Form2` нажмите клавиши CRTL+V, чтобы вставить в форму копию `elementHost1`.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="c1bd7-132">Скопированный элемент управления также имеет имя `elementHost1`, так как это закрытое поле класса `Form2`.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="c1bd7-133">Конфликта имен с `elementHost1` в классе `Form1` не возникает.</span><span class="sxs-lookup"><span data-stu-id="c1bd7-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1bd7-134">См. также</span><span class="sxs-lookup"><span data-stu-id="c1bd7-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="c1bd7-135">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="c1bd7-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="c1bd7-136">Использование элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="c1bd7-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="c1bd7-137">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="c1bd7-137">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
