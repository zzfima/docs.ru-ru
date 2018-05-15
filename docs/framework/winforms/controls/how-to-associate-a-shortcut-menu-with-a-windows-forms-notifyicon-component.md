---
title: Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms
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
ms.openlocfilehash: c0371dfb30c70bd2c4d98362abc7dc06926a5e88
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="a0aab-102">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0aab-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="a0aab-103">Несмотря на то что <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenuStrip> заменить и добавить функциональные возможности в <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> элементы управления предыдущих версий, <xref:System.Windows.Forms.MainMenu> и <xref:System.Windows.Forms.ContextMenu> можно сохранить для обратной совместимости и использования в будущем, если выбрать.</span><span class="sxs-lookup"><span data-stu-id="a0aab-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a0aab-104"><xref:System.Windows.Forms.NotifyIcon> Компонент отображает значок в области уведомлений панели задач.</span><span class="sxs-lookup"><span data-stu-id="a0aab-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="a0aab-105">Как правило приложения позволяют щелкните правой кнопкой мыши этот значок, чтобы отправлять команды в приложение, которое он представляет.</span><span class="sxs-lookup"><span data-stu-id="a0aab-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="a0aab-106">Связав <xref:System.Windows.Forms.ContextMenu> компонент с <xref:System.Windows.Forms.NotifyIcon> компонента, эти функции можно добавить в приложения.</span><span class="sxs-lookup"><span data-stu-id="a0aab-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0aab-107">Если требуется, чтобы свести к минимуму во время запуска при отображении экземпляра приложения <xref:System.Windows.Forms.NotifyIcon> набор компонентов на панели задач главной формы <xref:System.Windows.Forms.Form.WindowState%2A> свойства <xref:System.Windows.Forms.FormWindowState.Minimized> и убедитесь, что <xref:System.Windows.Forms.NotifyIcon> компонента <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойство имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="a0aab-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="a0aab-108">Чтобы связать контекстное меню с компонентом NotifyIcon во время разработки</span><span class="sxs-lookup"><span data-stu-id="a0aab-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="a0aab-109">Добавить <xref:System.Windows.Forms.NotifyIcon> компонента в форму и задайте важные свойства, такие как <xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="a0aab-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="a0aab-110">Дополнительные сведения см. в разделе [как: добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span><span class="sxs-lookup"><span data-stu-id="a0aab-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="a0aab-111">Добавить <xref:System.Windows.Forms.ContextMenu> в форме Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a0aab-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="a0aab-112">Добавление элементов меню в контекстное меню, представляющие команды, что вы хотите сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a0aab-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="a0aab-113">Это подходящий момент, чтобы добавить дополнительные функции меню этих пунктов меню, таких как ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="a0aab-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="a0aab-114">Задать <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> в контекстное меню, которое вы добавили компонент.</span><span class="sxs-lookup"><span data-stu-id="a0aab-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a0aab-115">При щелчке значка на панели задач, отображается в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="a0aab-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="a0aab-116">Чтобы связать контекстное меню с компонентом NotifyIcon программным способом</span><span class="sxs-lookup"><span data-stu-id="a0aab-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="a0aab-117">Создайте экземпляр класса <xref:System.Windows.Forms.NotifyIcon> класса и <xref:System.Windows.Forms.ContextMenu> класса, независимо от настройки свойства, необходимые для приложения (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> и <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойства <xref:System.Windows.Forms.NotifyIcon> компонент, пункты меню для <xref:System.Windows.Forms.ContextMenu> компонент).</span><span class="sxs-lookup"><span data-stu-id="a0aab-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="a0aab-118">Задать <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> свойство <xref:System.Windows.Forms.NotifyIcon> в контекстное меню, которое вы добавили компонент.</span><span class="sxs-lookup"><span data-stu-id="a0aab-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="a0aab-119">При щелчке значка на панели задач, отображается в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="a0aab-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a0aab-120">В следующем примере кода создается базовая структура меню.</span><span class="sxs-lookup"><span data-stu-id="a0aab-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="a0aab-121">Необходимо будет подставить те пункты меню, которые соответствуют приложение, которое вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="a0aab-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="a0aab-122">Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.MenuItem.Click> событий для этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="a0aab-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
>  <span data-ttu-id="a0aab-123">Необходимо инициализировать `notifyIcon1` и `contextMenu1,` это можно сделать, включив в конструктор формы следующие инструкции:</span><span class="sxs-lookup"><span data-stu-id="a0aab-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0aab-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a0aab-124">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="a0aab-125">Практическое руководство. Добавление значков приложения на панель задач с помощью компонента NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0aab-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [<span data-ttu-id="a0aab-126">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a0aab-126">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="a0aab-127">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="a0aab-127">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
