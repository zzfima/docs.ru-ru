---
title: "Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d795df8e8b514345632491fd6afdd618c2f18ec2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="ce254-102">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce254-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="ce254-103">Windows Forms <xref:System.Windows.Forms.NotifyIcon> компонент выводит один значок в области уведомлений панели задач.</span><span class="sxs-lookup"><span data-stu-id="ce254-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="ce254-104">Чтобы отобразить несколько значков в области состояния, необходимо иметь несколько <xref:System.Windows.Forms.NotifyIcon> компонентов в форме.</span><span class="sxs-lookup"><span data-stu-id="ce254-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="ce254-105">Чтобы задать значок, отображаемый для элемента управления, используйте <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ce254-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="ce254-106">Также можно написать код <xref:System.Windows.Forms.NotifyIcon.DoubleClick> обработчика событий, так что-то происходит, когда пользователь дважды щелкает значок.</span><span class="sxs-lookup"><span data-stu-id="ce254-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="ce254-107">Например может сделать диалоговое окно отображается для пользователя настроить фоновый процесс, представленный этим значком.</span><span class="sxs-lookup"><span data-stu-id="ce254-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce254-108"><xref:System.Windows.Forms.NotifyIcon> Компонент используется только, чтобы оповестить пользователей о возникших на действие или событие, или произошли изменения в состояние какая-либо.</span><span class="sxs-lookup"><span data-stu-id="ce254-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="ce254-109">Следует использовать меню, панелей инструментов и других элементов пользовательского интерфейса для обычных операций взаимодействия с приложениями.</span><span class="sxs-lookup"><span data-stu-id="ce254-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="ce254-110">Для задания значка</span><span class="sxs-lookup"><span data-stu-id="ce254-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="ce254-111">Присвоить значение <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="ce254-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="ce254-112">Значение должно быть типа `System.Drawing.Icon` и может быть загружена из ICO-файл.</span><span class="sxs-lookup"><span data-stu-id="ce254-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="ce254-113">Файл значка можно указать в коде или нажав кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.NotifyIcon.Icon%2A> свойство в  **Свойства** окна, а затем выбрав нужный файл в **откройте** появившемся.</span><span class="sxs-lookup"><span data-stu-id="ce254-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="ce254-114">Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ce254-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="ce254-115">Задать <xref:System.Windows.Forms.NotifyIcon.Text%2A> свойства соответствующую строку всплывающей подсказки.</span><span class="sxs-lookup"><span data-stu-id="ce254-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="ce254-116">В следующем примере кода путь задан для находится значок **Мои документы** папки.</span><span class="sxs-lookup"><span data-stu-id="ce254-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="ce254-117">Это расположение используется, так как предполагается, что большинство компьютеров под управлением операционной системы Windows будет содержать эта папка.</span><span class="sxs-lookup"><span data-stu-id="ce254-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="ce254-118">Эта папка также пользователи с уровнями доступа минимальные системные безопасно выполнить приложение.</span><span class="sxs-lookup"><span data-stu-id="ce254-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="ce254-119">В следующем примере требуется форма с <xref:System.Windows.Forms.NotifyIcon> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="ce254-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="ce254-120">Также требуется файл значка с именем `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="ce254-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ce254-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ce254-121">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="ce254-122">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ce254-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [<span data-ttu-id="ce254-123">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="ce254-123">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="ce254-124">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="ce254-124">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
