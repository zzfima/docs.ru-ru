---
title: Добавление значков приложений на панель задач с компонентом NotifyIcon
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
ms.openlocfilehash: 46b50ecaabe75dba08fea922d7b5639031692269
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746244"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="2c9c3-102">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c9c3-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>

<span data-ttu-id="2c9c3-103">Компонент Windows Forms <xref:System.Windows.Forms.NotifyIcon> отображает один значок в области уведомлений о состоянии панели задач.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="2c9c3-104">Чтобы в области состояния отображалось несколько значков, в форме необходимо несколько <xref:System.Windows.Forms.NotifyIcon> компонентов.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="2c9c3-105">Чтобы задать значок, отображаемый для элемента управления, используйте свойство <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="2c9c3-106">Можно также написать код в обработчике <xref:System.Windows.Forms.NotifyIcon.DoubleClick> событий, чтобы что-то происходит при двойном щелчке значка пользователем.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="2c9c3-107">Например, можно открыть диалоговое окно, чтобы пользователь мог настроить фоновый процесс, представленный значком.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>

> [!NOTE]
> <span data-ttu-id="2c9c3-108">Компонент <xref:System.Windows.Forms.NotifyIcon> используется только в целях уведомления, чтобы предупредить пользователей о том, что произошло действие или событие, либо изменилось состояние некоторой сортировки.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="2c9c3-109">Для стандартного взаимодействия с приложениями следует использовать меню, панели инструментов и другие элементы пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>

### <a name="to-set-the-icon"></a><span data-ttu-id="2c9c3-110">Установка значка</span><span class="sxs-lookup"><span data-stu-id="2c9c3-110">To set the icon</span></span>

1. <span data-ttu-id="2c9c3-111">Присвойте значение свойству <xref:System.Windows.Forms.NotifyIcon.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="2c9c3-112">Значение должно иметь тип `System.Drawing.Icon` и может быть загружено из файла ICO.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="2c9c3-113">Файл значка можно указать в коде или нажав кнопку с многоточием (![многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.NotifyIcon.Icon%2A> в окне " **Свойства** ", а затем выбрать файл в появившемся **диалоговом** окне.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-113">You can specify the icon file in code or by clicking the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>

2. <span data-ttu-id="2c9c3-114">Установите свойство <xref:System.Windows.Forms.NotifyIcon.Visible%2A> в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>

3. <span data-ttu-id="2c9c3-115">Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.Text%2A> соответствующую строку подсказки.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>

     <span data-ttu-id="2c9c3-116">В следующем примере кода путь, заданный для расположения значка, — это папка **Мои документы** .</span><span class="sxs-lookup"><span data-stu-id="2c9c3-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="2c9c3-117">Это расположение используется, поскольку можно предположить, что большинство компьютеров, работающих под управлением операционной системы Windows, будут содержать эту папку.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="2c9c3-118">Выбор этого расположения также позволяет пользователям с минимальными уровнями доступа к системе безопасно запускать приложение.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="2c9c3-119">В следующем примере требуется форма с уже добавленным элементом управления <xref:System.Windows.Forms.NotifyIcon>.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="2c9c3-120">Также требуется файл значка с именем `Icon.ico`.</span><span class="sxs-lookup"><span data-stu-id="2c9c3-120">It also requires an icon file named `Icon.ico`.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2c9c3-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c9c3-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="2c9c3-122">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2c9c3-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="2c9c3-123">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2c9c3-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="2c9c3-124">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2c9c3-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
