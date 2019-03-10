---
title: Практическое руководство. Добавление кнопок в элемент управления ToolBar
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: 78a58a8d-1041-4e38-9219-4096fa6a5c5c
ms.openlocfilehash: 347ca067a5ae5544351f29afe3ebcfe11d0b1e0f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713264"
---
# <a name="how-to-add-buttons-to-a-toolbar-control"></a><span data-ttu-id="4726e-102">Практическое руководство. Добавление кнопок в элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="4726e-102">How to: Add Buttons to a ToolBar Control</span></span>
> [!NOTE]
>  <span data-ttu-id="4726e-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> заменяет элемент управления <xref:System.Windows.Forms.ToolBar> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.ToolBar> можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="4726e-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="4726e-104">Неотъемлемой частью <xref:System.Windows.Forms.ToolBar> элемент управления — кнопки, добавьте к нему.</span><span class="sxs-lookup"><span data-stu-id="4726e-104">An integral part of the <xref:System.Windows.Forms.ToolBar> control is the buttons you add to it.</span></span> <span data-ttu-id="4726e-105">Их можно использовать для обеспечения быстрого доступа к командам меню или в качестве альтернативы могут быть размещены в другой области пользовательского интерфейса приложения для представления пользователям, которые не доступны в структуре меню команд.</span><span class="sxs-lookup"><span data-stu-id="4726e-105">These can be used to provide easy access to menu commands or, alternately, they can be placed in another area of the user interface of your application to expose commands to your users that are not available in the menu structure.</span></span>  
  
 <span data-ttu-id="4726e-106">В приведенных ниже примерах предполагается, что <xref:System.Windows.Forms.ToolBar> элемент управления добавлен в форму Windows (`Form1`).</span><span class="sxs-lookup"><span data-stu-id="4726e-106">The examples below assume that a <xref:System.Windows.Forms.ToolBar> control has been added to a Windows Form (`Form1`).</span></span>  
  
### <a name="to-add-buttons-programmatically"></a><span data-ttu-id="4726e-107">Добавление кнопок программными средствами</span><span class="sxs-lookup"><span data-stu-id="4726e-107">To add buttons programmatically</span></span>  
  
1.  <span data-ttu-id="4726e-108">В процедуре создания кнопки панели инструментов, добавив их в <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> коллекции.</span><span class="sxs-lookup"><span data-stu-id="4726e-108">In a procedure, create toolbar buttons by adding them to the <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection.</span></span>  
  
2.  <span data-ttu-id="4726e-109">Задайте значения свойств отдельных кнопок, передав индекс кнопки с помощью <xref:System.Windows.Forms.ToolBar.Buttons%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4726e-109">Specify property settings for an individual button by passing the button's index via the <xref:System.Windows.Forms.ToolBar.Buttons%2A> property.</span></span>  
  
     <span data-ttu-id="4726e-110">В приведенном ниже примере предполагается, что форма <xref:System.Windows.Forms.ToolBar> управления уже добавлен.</span><span class="sxs-lookup"><span data-stu-id="4726e-110">The example below assumes a form with a <xref:System.Windows.Forms.ToolBar> control already added.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4726e-111"><xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> Коллекция является коллекция (с нуля), поэтому код должен продолжаться соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="4726e-111">The <xref:System.Windows.Forms.ToolBar.Buttons%2A?displayProperty=nameWithType> collection is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateToolBarButtons()  
    ' Create buttons and set text property.  
       ToolBar1.Buttons.Add("One")  
       ToolBar1.Buttons.Add("Two")  
       ToolBar1.Buttons.Add("Three")  
       ToolBar1.Buttons.Add("Four")  
    ' Set properties of StatusBar panels.  
    ' Set Style property.  
       ToolBar1.Buttons(0).Style = ToolBarButtonStyle.PushButton  
       ToolBar1.Buttons(1).Style = ToolBarButtonStyle.Separator  
       ToolBar1.Buttons(2).Style = ToolBarButtonStyle.ToggleButton  
       ToolBar1.Buttons(3).Style = ToolBarButtonStyle.DropDownButton  
    ' Set the ToggleButton's PartialPush property.  
       ToolBar1.Buttons(2).PartialPush = True  
    ' Instantiate a ContextMenu component and menu items.  
    ' Set the DropDownButton's DropDownMenu property to the context menu.  
       Dim cm As New ContextMenu()  
       Dim miOne As New MenuItem("One")  
       Dim miTwo As New MenuItem("Two")  
       Dim miThree As New MenuItem("Three")  
       cm.MenuItems.Add(miOne)  
       cm.MenuItems.Add(miTwo)  
       cm.MenuItems.Add(miThree)  
       ToolBar1.Buttons(3).DropDownMenu = cm  
    ' Set the PushButton's Pushed property.  
       ToolBar1.Buttons(0).Pushed = True  
    ' Set the ToolTipText property of one of the buttons.  
       ToolBar1.Buttons(1).ToolTipText = "Button 2"  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateToolBarButtons()  
    {  
       // Create buttons and set text property.  
       toolBar1.Buttons.Add("One");  
       toolBar1.Buttons.Add("Two");  
       toolBar1.Buttons.Add("Three");  
       toolBar1.Buttons.Add("Four");  
  
       // Set properties of StatusBar panels.  
       // Set Style property.  
       toolBar1.Buttons[0].Style = ToolBarButtonStyle.PushButton;  
       toolBar1.Buttons[1].Style = ToolBarButtonStyle.Separator;  
       toolBar1.Buttons[2].Style = ToolBarButtonStyle.ToggleButton;  
       toolBar1.Buttons[3].Style = ToolBarButtonStyle.DropDownButton;  
  
       // Set the ToggleButton's PartialPush property.  
       toolBar1.Buttons[2].PartialPush = true;  
  
       // Instantiate a ContextMenu component and menu items.  
       // Set the DropDownButton's DropDownMenu property to   
       // the context menu.  
       ContextMenu cm = new ContextMenu();  
       MenuItem miOne = new MenuItem("One");  
       MenuItem miTwo = new MenuItem("Two");  
       MenuItem miThree = new MenuItem("Three");  
       cm.MenuItems.Add(miOne);  
       cm.MenuItems.Add(miTwo);  
       cm.MenuItems.Add(miThree);  
  
       toolBar1.Buttons[3].DropDownMenu = cm;  
       // Set the PushButton's Pushed property.  
       toolBar1.Buttons[0].Pushed = true;  
       // Set the ToolTipText property of 1 of the buttons.  
       toolBar1.Buttons[1].ToolTipText = "Button 2";  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateToolBarButtons()  
       {  
          // Create buttons and set text property.  
          toolBar1->Buttons->Add( "One" );  
          toolBar1->Buttons->Add( "Two" );  
          toolBar1->Buttons->Add( "Three" );  
          toolBar1->Buttons->Add( "Four" );  
  
          // Set properties of StatusBar panels.  
          // Set Style property.  
          toolBar1->Buttons[0]->Style = ToolBarButtonStyle::PushButton;  
          toolBar1->Buttons[1]->Style = ToolBarButtonStyle::Separator;  
          toolBar1->Buttons[2]->Style = ToolBarButtonStyle::ToggleButton;  
          toolBar1->Buttons[3]->Style = ToolBarButtonStyle::DropDownButton;  
  
          // Set the ToggleButton's PartialPush property.  
          toolBar1->Buttons[2]->PartialPush = true;  
  
          // Instantiate a ContextMenu component and menu items.  
          // Set the DropDownButton's DropDownMenu property to   
          // the context menu.  
          System::Windows::Forms::ContextMenu^ cm = gcnew System::Windows::Forms::ContextMenu;  
          MenuItem^ miOne = gcnew MenuItem( "One" );  
          MenuItem^ miTwo = gcnew MenuItem( "Two" );  
          MenuItem^ miThree = gcnew MenuItem( "Three" );  
          cm->MenuItems->Add( miOne );  
          cm->MenuItems->Add( miTwo );  
          cm->MenuItems->Add( miThree );  
          toolBar1->Buttons[3]->DropDownMenu = cm;  
  
          // Set the PushButton's Pushed property.  
          toolBar1->Buttons[0]->Pushed = true;  
  
          // Set the ToolTipText property of 1 of the buttons.  
          toolBar1->Buttons[1]->ToolTipText = "Button 2";  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4726e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4726e-112">See also</span></span>
- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="4726e-113">Практическое руководство. Определение значка для кнопки панели инструментов</span><span class="sxs-lookup"><span data-stu-id="4726e-113">How to: Define an Icon for a ToolBar Button</span></span>](how-to-define-an-icon-for-a-toolbar-button.md)
- [<span data-ttu-id="4726e-114">Практическое руководство. Триггер событий меню для кнопок панели инструментов</span><span class="sxs-lookup"><span data-stu-id="4726e-114">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="4726e-115">Общие сведения об элементе управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="4726e-115">ToolBar Control Overview</span></span>](toolbar-control-overview-windows-forms.md)
- [<span data-ttu-id="4726e-116">Элемент управления ToolBar</span><span class="sxs-lookup"><span data-stu-id="4726e-116">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
