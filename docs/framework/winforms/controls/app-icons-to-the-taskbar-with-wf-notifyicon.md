---
title: Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 52c18b959361079aac6b95dc5d4584bf464a306a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640327"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="b6699-102">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6699-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="b6699-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> компонент отображает один значок в области уведомлений панели задач.</span><span class="sxs-lookup"><span data-stu-id="b6699-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="b6699-104">Чтобы отобразить несколько значков в области состояния, необходимо иметь несколько <xref:System.Windows.Forms.NotifyIcon> компонентов в форме.</span><span class="sxs-lookup"><span data-stu-id="b6699-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="b6699-105">Чтобы задать значок, отображаемый для элемента управления, используйте <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b6699-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="b6699-106">Можно также написать код <xref:System.Windows.Forms.NotifyIcon.DoubleClick> обработчик событий, так что-то происходит, когда пользователь дважды щелкает значок.</span><span class="sxs-lookup"><span data-stu-id="b6699-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="b6699-107">Например вы можете создать диалоговое окно отображается для пользователя настроить фоновый процесс, представленный этим значком.</span><span class="sxs-lookup"><span data-stu-id="b6699-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6699-108"><xref:System.Windows.Forms.NotifyIcon> Компонент используется только, чтобы оповестить пользователей о возникших на действие или событие, или произошло изменение в состоянии какого-либо рода.</span><span class="sxs-lookup"><span data-stu-id="b6699-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="b6699-109">Следует использовать меню, панелей инструментов и других элементов пользовательского интерфейса для стандартное взаимодействие с приложениями.</span><span class="sxs-lookup"><span data-stu-id="b6699-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="b6699-110">Чтобы задать значок</span><span class="sxs-lookup"><span data-stu-id="b6699-110">To set the icon</span></span>  
  
1. <span data-ttu-id="b6699-111">Присвойте значение <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="b6699-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="b6699-112">Значение должно быть типа `System.Drawing.Icon` и может быть загружена из ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="b6699-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="b6699-113">Файл значка можно указать в коде или нажав кнопку с многоточием (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство в  **Свойства** окна, а затем выбрав файл в **откройте** диалоговое окно, которое отображается.</span><span class="sxs-lookup"><span data-stu-id="b6699-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2. <span data-ttu-id="b6699-114">Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="b6699-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="b6699-115">Задайте <xref:System.Windows.Forms.NotifyIcon.Text%2A> свойство соответствующую строку всплывающей подсказки.</span><span class="sxs-lookup"><span data-stu-id="b6699-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="b6699-116">В следующем примере кода, задайте путь — расположение значка **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="b6699-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="b6699-117">Это расположение используется в том случае, так как можно предположить, что большинство компьютеров под управлением ОС Windows будет включать эту папку.</span><span class="sxs-lookup"><span data-stu-id="b6699-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="b6699-118">Эта папка также позволяет уровень доступа к минимальным системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="b6699-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="b6699-119">В следующем примере требуется форма с <xref:System.Windows.Forms.NotifyIcon> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="b6699-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="b6699-120">Он также требуется файл значка с именем `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="b6699-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6699-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b6699-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="b6699-122">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b6699-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="b6699-123">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="b6699-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="b6699-124">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="b6699-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
