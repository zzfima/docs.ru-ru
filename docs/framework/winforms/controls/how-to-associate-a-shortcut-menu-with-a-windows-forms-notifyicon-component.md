---
title: Связывание контекстного меню с компонентом NotifyIcon
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
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742045"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="7cd34-102">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cd34-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="7cd34-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функции в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> сохраняются для обратной совместимости и использования в будущем при выборе.</span><span class="sxs-lookup"><span data-stu-id="7cd34-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="7cd34-104">Компонент <xref:System.Windows.Forms.NotifyIcon> отображает значок в области уведомления о состоянии панели задач.</span><span class="sxs-lookup"><span data-stu-id="7cd34-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="7cd34-105">Обычно приложения позволяют щелкнуть этот значок правой кнопкой мыши, чтобы отправить команды в приложение, которое оно представляет.</span><span class="sxs-lookup"><span data-stu-id="7cd34-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="7cd34-106">Связав компонент <xref:System.Windows.Forms.ContextMenu> с компонентом <xref:System.Windows.Forms.NotifyIcon>, можно добавить эту функцию в приложения.</span><span class="sxs-lookup"><span data-stu-id="7cd34-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7cd34-107">Если необходимо, чтобы приложение было свернуто при запуске при отображении экземпляра компонента <xref:System.Windows.Forms.NotifyIcon> на панели задач, установите для свойства <xref:System.Windows.Forms.Form.WindowState%2A> главной формы значение <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что для свойства <xref:System.Windows.Forms.NotifyIcon.Visible%2A> компонента <xref:System.Windows.Forms.NotifyIcon> задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="7cd34-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="7cd34-108">Связывание контекстного меню с компонентом NotifyIcon во время разработки</span><span class="sxs-lookup"><span data-stu-id="7cd34-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="7cd34-109">Добавьте в форму компонент <xref:System.Windows.Forms.NotifyIcon> и задайте важные свойства, такие как свойства <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.</span><span class="sxs-lookup"><span data-stu-id="7cd34-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="7cd34-110">Дополнительные сведения см. в разделе [как добавить значки приложений на панель задач с помощью компонента Windows Forms NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="7cd34-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="7cd34-111">Добавьте <xref:System.Windows.Forms.ContextMenu> компонент в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7cd34-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="7cd34-112">Добавьте пункты меню в контекстное меню, представляющее команды, которые необходимо сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="7cd34-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="7cd34-113">Кроме того, это очень удобно для добавления улучшений меню к этим пунктам меню, таким как ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="7cd34-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="7cd34-114">Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстное меню, которое вы добавили.</span><span class="sxs-lookup"><span data-stu-id="7cd34-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="7cd34-115">Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="7cd34-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="7cd34-116">Связывание контекстного меню с компонентом NotifyIcon программным способом</span><span class="sxs-lookup"><span data-stu-id="7cd34-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="7cd34-117">Создайте экземпляр класса <xref:System.Windows.Forms.NotifyIcon> и класс <xref:System.Windows.Forms.ContextMenu> с любыми настройками свойств для приложения (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства для компонента <xref:System.Windows.Forms.NotifyIcon>, элементы меню для компонента <xref:System.Windows.Forms.ContextMenu>).</span><span class="sxs-lookup"><span data-stu-id="7cd34-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="7cd34-118">Задайте для свойства <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> компонента <xref:System.Windows.Forms.NotifyIcon> контекстное меню, которое вы добавили.</span><span class="sxs-lookup"><span data-stu-id="7cd34-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="7cd34-119">Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="7cd34-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7cd34-120">В следующем примере кода создается базовая структура меню.</span><span class="sxs-lookup"><span data-stu-id="7cd34-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="7cd34-121">Вам потребуется настроить параметры меню для тех, которые соответствуют разрабатываемому приложению.</span><span class="sxs-lookup"><span data-stu-id="7cd34-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="7cd34-122">Кроме того, необходимо написать код для управления событиями <xref:System.Windows.Forms.MenuItem.Click> для этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="7cd34-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
> <span data-ttu-id="7cd34-123">Необходимо инициализировать `notifyIcon1` и `contextMenu1,`, которые можно сделать, включив в конструктор формы следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="7cd34-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="7cd34-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7cd34-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="7cd34-125">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7cd34-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="7cd34-126">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="7cd34-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="7cd34-127">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="7cd34-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
