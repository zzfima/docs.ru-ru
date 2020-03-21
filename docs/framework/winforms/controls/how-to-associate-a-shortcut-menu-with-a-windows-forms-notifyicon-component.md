---
title: Ассоциированное меню ярлыка с компонентом NotifyIcon
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182255"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="15322-102">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15322-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="15322-103">Хотя <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> и заменить и <xref:System.Windows.Forms.MainMenu> добавить функциональность и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются как для обратной совместимости и будущего использования, если вы выбираете.</span><span class="sxs-lookup"><span data-stu-id="15322-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="15322-104">Компонент <xref:System.Windows.Forms.NotifyIcon> отображает значок в области уведомления о состоянии панели задач.</span><span class="sxs-lookup"><span data-stu-id="15322-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="15322-105">Как правило, приложения позволяют нажать на эту иконку, чтобы отправить команды в приложение, которое оно представляет.</span><span class="sxs-lookup"><span data-stu-id="15322-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="15322-106">Связывая <xref:System.Windows.Forms.ContextMenu> компонент с <xref:System.Windows.Forms.NotifyIcon> компонентом, можно добавить эту функциональность в приложения.</span><span class="sxs-lookup"><span data-stu-id="15322-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15322-107">Если вы хотите, чтобы ваше приложение было сведено к <xref:System.Windows.Forms.NotifyIcon> минимуму при запуске при отображении <xref:System.Windows.Forms.Form.WindowState%2A> экземпляра компонента в панели задач, установите свойство основной формы <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что свойство <xref:System.Windows.Forms.NotifyIcon> компонента <xref:System.Windows.Forms.NotifyIcon.Visible%2A> настроено на `true`.</span><span class="sxs-lookup"><span data-stu-id="15322-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="15322-108">Связать меню ярлыка с компонентом NotifyIcon во время проектирования</span><span class="sxs-lookup"><span data-stu-id="15322-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="15322-109">Добавьте <xref:System.Windows.Forms.NotifyIcon> компонент в форму и установите важные <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства, такие как свойства и свойства.</span><span class="sxs-lookup"><span data-stu-id="15322-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="15322-110">Для получения дополнительной информации [см. Как: Добавить значки приложений в панель задач с компонентом NotifyIcon Windows.](app-icons-to-the-taskbar-with-wf-notifyicon.md)</span><span class="sxs-lookup"><span data-stu-id="15322-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="15322-111">Добавьте <xref:System.Windows.Forms.ContextMenu> компонент в форму Windows.</span><span class="sxs-lookup"><span data-stu-id="15322-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="15322-112">Добавьте элементы меню в меню ярлыка, представляющие команды, которые вы хотите сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="15322-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="15322-113">Это также хорошее время, чтобы добавить улучшения меню к этим пунктам меню, таким как ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="15322-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="15322-114">Установите <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> компонента в меню ярлыка, которое вы добавили.</span><span class="sxs-lookup"><span data-stu-id="15322-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="15322-115">С помощью этого набора свойств меню ярлыка будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="15322-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="15322-116">Связать меню ярлыка с компонентом NotifyIcon программно</span><span class="sxs-lookup"><span data-stu-id="15322-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="15322-117">Создайте экземпляр <xref:System.Windows.Forms.NotifyIcon> класса и <xref:System.Windows.Forms.ContextMenu> класса с любыми настройками свойств,<xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> необходимыми <xref:System.Windows.Forms.NotifyIcon> для приложения (и <xref:System.Windows.Forms.ContextMenu> свойствами для компонента, пунктами меню для компонента).</span><span class="sxs-lookup"><span data-stu-id="15322-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="15322-118">Установите <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> компонента в меню ярлыка, которое вы добавили.</span><span class="sxs-lookup"><span data-stu-id="15322-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="15322-119">С помощью этого набора свойств меню ярлыка будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="15322-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="15322-120">Следующий пример кода создает основную структуру меню.</span><span class="sxs-lookup"><span data-stu-id="15322-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="15322-121">Вам нужно будет настроить выбор меню для тех, которые соответствуют приложению, которое вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="15322-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="15322-122">Кроме того, вы хотите написать <xref:System.Windows.Forms.MenuItem.Click> код для обработки событий для этих элементов меню.</span><span class="sxs-lookup"><span data-stu-id="15322-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> <span data-ttu-id="15322-123">Вы должны `notifyIcon1` инициализировать и `contextMenu1,` что вы можете сделать, включив следующие утверждения в конструктор вашей формы:</span><span class="sxs-lookup"><span data-stu-id="15322-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="15322-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15322-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="15322-125">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="15322-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="15322-126">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="15322-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="15322-127">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="15322-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
