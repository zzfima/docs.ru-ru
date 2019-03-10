---
title: Практическое руководство. Настройка добавления элемента с помощью компонента BindingSource в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], creating new items
- BindingSource component [Windows Forms], customizing item addition with
- examples [Windows Forms], BindingSource component
- BindingSource component [Windows Forms], examples
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
ms.openlocfilehash: f199fd55262b1b72bf8bc1a133a09b80db95c27a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722936"
---
# <a name="how-to-customize-item-addition-with-the-windows-forms-bindingsource"></a><span data-ttu-id="22d1d-102">Практическое руководство. Настройка добавления элемента с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="22d1d-102">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>
<span data-ttu-id="22d1d-103">При использовании компонента <xref:System.Windows.Forms.BindingSource> для привязки элемента управления Windows Forms к источнику данных может потребоваться настроить создание новых элементов.</span><span class="sxs-lookup"><span data-stu-id="22d1d-103">When you use a <xref:System.Windows.Forms.BindingSource> component to bind a Windows Forms control to a data source, you may find it necessary to customize the creation of new items.</span></span> <span data-ttu-id="22d1d-104">Компонент <xref:System.Windows.Forms.BindingSource> упрощает эту процедуру, предоставляя событие <xref:System.Windows.Forms.BindingSource.AddingNew> , которое обычно происходит, когда связанный элемент управления должен создать новый элемент.</span><span class="sxs-lookup"><span data-stu-id="22d1d-104">The <xref:System.Windows.Forms.BindingSource> component makes this straightforward by providing the <xref:System.Windows.Forms.BindingSource.AddingNew> event, which is typically raised when the bound control needs to create a new item.</span></span> <span data-ttu-id="22d1d-105">Обработчик событий может обеспечивать любое необходимое поведение (например, вызов метода веб-службы или получение нового объекта из фабрики класса).</span><span class="sxs-lookup"><span data-stu-id="22d1d-105">Your event handler can provide whatever custom behavior is required (for example, calling a method on a Web service or getting a new object from a class factory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22d1d-106">Добавление элемента с помощью события <xref:System.Windows.Forms.BindingSource.AddingNew> отменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="22d1d-106">When an item is added by handling the <xref:System.Windows.Forms.BindingSource.AddingNew> event, the addition cannot be canceled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22d1d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="22d1d-107">Example</span></span>  
 <span data-ttu-id="22d1d-108">В примере ниже показано, как связать элемент управления <xref:System.Windows.Forms.DataGridView> с фабрикой класса с помощью компонента <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="22d1d-108">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a class factory by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="22d1d-109">Когда пользователь щелкает новую строку элемента управления <xref:System.Windows.Forms.DataGridView> , вызывается событие <xref:System.Windows.Forms.BindingSource.AddingNew> .</span><span class="sxs-lookup"><span data-stu-id="22d1d-109">When the user clicks the <xref:System.Windows.Forms.DataGridView> control's new row, the <xref:System.Windows.Forms.BindingSource.AddingNew> event is raised.</span></span> <span data-ttu-id="22d1d-110">Обработчик событий создает объект `DemoCustomer`, который присваивается свойству <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22d1d-110">The event handler creates a new `DemoCustomer` object, which is assigned to the <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="22d1d-111">В результате новый объект `DemoCustomer` добавляется к списку компонентов <xref:System.Windows.Forms.BindingSource> и отображается в новой строке элемента управления <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="22d1d-111">This causes the new `DemoCustomer` object to be added to the <xref:System.Windows.Forms.BindingSource> component's list and to be displayed in the new row of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22d1d-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="22d1d-112">Compiling the Code</span></span>  
 <span data-ttu-id="22d1d-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="22d1d-113">This example requires:</span></span>  
  
-   <span data-ttu-id="22d1d-114">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="22d1d-114">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="22d1d-115">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="22d1d-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="22d1d-116">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="22d1d-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22d1d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="22d1d-117">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="22d1d-118">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="22d1d-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="22d1d-119">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="22d1d-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
