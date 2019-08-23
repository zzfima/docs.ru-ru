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
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922769"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="2e623-102">Практическое руководство. Связывание контекстного меню с компонентом NotifyIcon в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2e623-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="2e623-103">Хотя <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> заменяют и добавляют функции к элементам управления и предыдущих версий и сохраняются для обратной совместимости и использования в будущем при выборе. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="2e623-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="2e623-104"><xref:System.Windows.Forms.NotifyIcon> Компонент отображает значок в области уведомлений о состоянии панели задач.</span><span class="sxs-lookup"><span data-stu-id="2e623-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="2e623-105">Обычно приложения позволяют щелкнуть этот значок правой кнопкой мыши, чтобы отправить команды в приложение, которое оно представляет.</span><span class="sxs-lookup"><span data-stu-id="2e623-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="2e623-106">Связав <xref:System.Windows.Forms.ContextMenu> компонент<xref:System.Windows.Forms.NotifyIcon> с компонентом, можно добавить эту функцию в приложения.</span><span class="sxs-lookup"><span data-stu-id="2e623-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e623-107">Если необходимо, чтобы приложение было свернуто при запуске при <xref:System.Windows.Forms.NotifyIcon> отображении экземпляра компонента на панели задач, установите <xref:System.Windows.Forms.Form.WindowState%2A> свойство основной формы в <xref:System.Windows.Forms.FormWindowState.Minimized> значение и убедитесь, <xref:System.Windows.Forms.NotifyIcon> что <xref:System.Windows.Forms.NotifyIcon.Visible%2A> свойство компонента имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="2e623-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="2e623-108">Связывание контекстного меню с компонентом NotifyIcon во время разработки</span><span class="sxs-lookup"><span data-stu-id="2e623-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="2e623-109">Добавьте в форму <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> компонент и задайте важные свойства, такие как свойства и. <xref:System.Windows.Forms.NotifyIcon></span><span class="sxs-lookup"><span data-stu-id="2e623-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="2e623-110">Дополнительные сведения см. в разделе [Практическое руководство. Добавьте значки приложений на панель задач с компонентом](app-icons-to-the-taskbar-with-wf-notifyicon.md)Windows Forms NotifyIcon.</span><span class="sxs-lookup"><span data-stu-id="2e623-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="2e623-111"><xref:System.Windows.Forms.ContextMenu> Добавьте компонент в форму Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2e623-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="2e623-112">Добавьте пункты меню в контекстное меню, представляющее команды, которые необходимо сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="2e623-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="2e623-113">Кроме того, это очень удобно для добавления улучшений меню к этим пунктам меню, таким как ключи доступа.</span><span class="sxs-lookup"><span data-stu-id="2e623-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="2e623-114">Присвойте <xref:System.Windows.Forms.NotifyIcon> свойству компонента значение, добавленное в контекстное меню. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A></span><span class="sxs-lookup"><span data-stu-id="2e623-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="2e623-115">Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="2e623-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="2e623-116">Связывание контекстного меню с компонентом NotifyIcon программным способом</span><span class="sxs-lookup"><span data-stu-id="2e623-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="2e623-117">Создайте экземпляр <xref:System.Windows.Forms.NotifyIcon> класса <xref:System.Windows.Forms.NotifyIcon> <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.NotifyIcon.Visible%2A> и класс с любыми настройками свойств для приложения (и свойствами для компонента, элементы меню для элемента <xref:System.Windows.Forms.ContextMenu> компонент).</span><span class="sxs-lookup"><span data-stu-id="2e623-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="2e623-118">Присвойте <xref:System.Windows.Forms.NotifyIcon> свойству компонента значение, добавленное в контекстное меню. <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A></span><span class="sxs-lookup"><span data-stu-id="2e623-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="2e623-119">Если это свойство установлено, контекстное меню будет отображаться при нажатии значка на панели задач.</span><span class="sxs-lookup"><span data-stu-id="2e623-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="2e623-120">В следующем примере кода создается базовая структура меню.</span><span class="sxs-lookup"><span data-stu-id="2e623-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="2e623-121">Вам потребуется настроить параметры меню для тех, которые соответствуют разрабатываемому приложению.</span><span class="sxs-lookup"><span data-stu-id="2e623-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="2e623-122">Кроме того, необходимо написать код для управления <xref:System.Windows.Forms.MenuItem.Click> событиями этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="2e623-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
> <span data-ttu-id="2e623-123">Для этого необходимо `notifyIcon1` выполнить `contextMenu1,` инициализацию, включив в конструктор формы следующие операторы:</span><span class="sxs-lookup"><span data-stu-id="2e623-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e623-124">См. также</span><span class="sxs-lookup"><span data-stu-id="2e623-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="2e623-125">Практическое руководство. Добавление значков приложений на панель задач с компонентом Windows Forms NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2e623-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="2e623-126">Компонент NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2e623-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="2e623-127">Общие сведения о компоненте управления NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="2e623-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
