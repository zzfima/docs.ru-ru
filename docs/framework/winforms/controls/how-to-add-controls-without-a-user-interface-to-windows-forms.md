---
title: Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 9458fc7f3344a5692581485a0e5bd462e45551d9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731992"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="a638b-102">Практическое руководство. Добавление элементов управления, для которых не существует пользовательского интерфейса, в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="a638b-103">Невизуального элемента управления (или компонент) предоставляет функциональные возможности приложения.</span><span class="sxs-lookup"><span data-stu-id="a638b-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="a638b-104">В отличие от других элементов управления компоненты не предоставляют пользовательский интерфейс для пользователя и таким образом не обязательно должны отображаться в рабочей области конструктора Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a638b-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="a638b-105">При добавлении компонента в форму, в конструкторе Windows Forms отображает изменяемого в нижней части формы, в которой отображаются все компоненты.</span><span class="sxs-lookup"><span data-stu-id="a638b-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="a638b-106">После добавления элемента управления в область компонентов, можно выбрать компонент и задайте свойства, как и любой другой элемент управления в форме.</span><span class="sxs-lookup"><span data-stu-id="a638b-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a638b-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="a638b-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a638b-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="a638b-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a638b-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="a638b-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="a638b-110">Добавление компонента в форму Windows</span><span class="sxs-lookup"><span data-stu-id="a638b-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="a638b-111">Откройте форму.</span><span class="sxs-lookup"><span data-stu-id="a638b-111">Open the form.</span></span> <span data-ttu-id="a638b-112">Дополнительные сведения см. в разделе [Практическое руководство. Отображение форм Windows Forms в конструкторе](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span><span class="sxs-lookup"><span data-stu-id="a638b-112">For details, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="a638b-113">На **панели элементов** щелкните компонент и перетащите его на форму.</span><span class="sxs-lookup"><span data-stu-id="a638b-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="a638b-114">Компонент появится в области компонентов.</span><span class="sxs-lookup"><span data-stu-id="a638b-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="a638b-115">Кроме того компоненты можно добавить в форму во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a638b-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="a638b-116">Это распространенный сценарий, особенно в том случае, поскольку компоненты не имеют визуального выражения, в отличие от элементов управления, имеющих пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="a638b-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="a638b-117">В следующем примере <xref:System.Windows.Forms.Timer> компонент добавляется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a638b-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="a638b-118">(Обратите внимание на то, что Visual Studio содержит ряд различных таймеров; в этом случае используйте форм Windows <xref:System.Windows.Forms.Timer> компонента.</span><span class="sxs-lookup"><span data-stu-id="a638b-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="a638b-119">Дополнительные сведения о различных таймеров в Visual Studio, см. в разделе [Общие сведения о серверных таймерах](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span><span class="sxs-lookup"><span data-stu-id="a638b-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a638b-120">Компоненты часто имеют особые свойства, которые должны быть заданы для их эффективной работы.</span><span class="sxs-lookup"><span data-stu-id="a638b-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="a638b-121">В случае использования компонента <xref:System.Windows.Forms.Timer> в приведенном ниже примере задается свойство `Interval`. </span><span class="sxs-lookup"><span data-stu-id="a638b-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="a638b-122">Убедитесь, что при добавлении компонентов в проект вы задаете необходимые свойства этих компонентов.</span><span class="sxs-lookup"><span data-stu-id="a638b-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="a638b-123">Добавление компонента в форму Windows программными средствами</span><span class="sxs-lookup"><span data-stu-id="a638b-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="a638b-124">Создайте экземпляр класса <xref:System.Windows.Forms.Timer> в коде.</span><span class="sxs-lookup"><span data-stu-id="a638b-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="a638b-125">Задайте свойство `Interval` для определения времени между тактами таймера.</span><span class="sxs-lookup"><span data-stu-id="a638b-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="a638b-126">Настройте другие необходимые свойства компонента.</span><span class="sxs-lookup"><span data-stu-id="a638b-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="a638b-127">В следующем коде показано создание <xref:System.Windows.Forms.Timer> и установка его свойства `Interval`.</span><span class="sxs-lookup"><span data-stu-id="a638b-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a638b-128">Создание ссылки на вредоносный элемент `UserControl` может поставить локальный компьютер под угрозу атаки по сети.</span><span class="sxs-lookup"><span data-stu-id="a638b-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="a638b-129">Это может произойти только в том случае, если злоумышленник создаст небезопасный пользовательский элемент управления, а затем вы по ошибке добавите его в проект.</span><span class="sxs-lookup"><span data-stu-id="a638b-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a638b-130">См. также</span><span class="sxs-lookup"><span data-stu-id="a638b-130">See Also</span></span>  
 [<span data-ttu-id="a638b-131">Элементы управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="a638b-132">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="a638b-133">Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="a638b-134">Практическое руководство. Копирование элементов управления между формами Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [<span data-ttu-id="a638b-135">Размещение элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="a638b-136">Создание меток и назначение сочетаний клавиш для элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="a638b-137">Элементы управления для использования в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="a638b-138">Функциональная классификация элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a638b-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
