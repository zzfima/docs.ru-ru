---
title: Практическое руководство. Переход между данными с помощью элемента управления BindingNavigator в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingNavigator control [Windows Forms], navigating data
- data [Windows Forms], navigating
- data navigation
- examples [Windows Forms], BindingNavigator control
ms.assetid: 0e5d4f34-bc9b-47cf-9b8d-93acbb1f1dbb
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a47273f9598b3776276c14d41e88f7f0dff5bed
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-navigate-data-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="1a3c1-102">Практическое руководство. Переход между данными с помощью элемента управления BindingNavigator в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a3c1-102">How to: Navigate Data with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="1a3c1-103">С появлением элемента управления <xref:System.Windows.Forms.BindingNavigator> в Windows Forms разработчики получили возможность предоставлять конечным пользователям простой пользовательский интерфейс для перехода и управления данными в формах, которые они создают.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-103">The advent of the <xref:System.Windows.Forms.BindingNavigator> control in Windows Forms enables developers to provide end users with a simple data navigation and manipulation user interface on the forms they create.</span></span>  
  
 <span data-ttu-id="1a3c1-104">Элемент управления <xref:System.Windows.Forms.BindingNavigator> является элементом управления <xref:System.Windows.Forms.ToolStrip> с кнопками, предварительно настроенными для перехода к первой, последней, следующей и предыдущей записям набора данных, а также для добавления и удаления записей.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-104">The <xref:System.Windows.Forms.BindingNavigator> control is a <xref:System.Windows.Forms.ToolStrip> control with buttons preconfigured for navigation to the first, last, next, and previous record in a data set, as well as buttons to add and delete records.</span></span> <span data-ttu-id="1a3c1-105">Добавить кнопки в элемент управления <xref:System.Windows.Forms.BindingNavigator> просто, так как это элемент управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-105">Adding buttons to the <xref:System.Windows.Forms.BindingNavigator> control is easy, because it is a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  <span data-ttu-id="1a3c1-106">См. также [Практическое руководство. Добавление кнопок загрузки, сохранения и отмены в элемент управления BindingNavigator в формах Windows Forms](http://msdn.microsoft.com/library/safa4957\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1a3c1-106">Also see [How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control](http://msdn.microsoft.com/library/safa4957\(v=vs.110\)).</span></span>  
  
 <span data-ttu-id="1a3c1-107">Каждой кнопке элемента управления <xref:System.Windows.Forms.BindingNavigator> соответствует член компонента <xref:System.Windows.Forms.BindingSource>, обеспечивающий ту же функциональность программным путем.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-107">For each button on the <xref:System.Windows.Forms.BindingNavigator> control, there is a corresponding member of the <xref:System.Windows.Forms.BindingSource> component that programmatically allows the same functionality.</span></span> <span data-ttu-id="1a3c1-108">Например, кнопка <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> соответствует методу <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> компонента <xref:System.Windows.Forms.BindingSource>, кнопка <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> соответствует методу <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> и т. д.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-108">For example, the <xref:System.Windows.Forms.BindingNavigator.MoveFirstItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.MoveFirst%2A> method of the <xref:System.Windows.Forms.BindingSource> component, the <xref:System.Windows.Forms.BindingNavigator.DeleteItem%2A> button corresponds to the <xref:System.Windows.Forms.BindingSource.RemoveCurrent%2A> method, and so on.</span></span> <span data-ttu-id="1a3c1-109">Таким образом, обеспечение перехода по данным с помощью элемента управления <xref:System.Windows.Forms.BindingNavigator> — простая процедура, требующая присвоения свойству <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> соответствующего компонента <xref:System.Windows.Forms.BindingSource> в форме.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-109">As a result, enabling the <xref:System.Windows.Forms.BindingNavigator> control to navigate data records is a simple as setting its <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the appropriate <xref:System.Windows.Forms.BindingSource> component on the form.</span></span>  
  
### <a name="to-set-up-the-bindingnavigator-control"></a><span data-ttu-id="1a3c1-110">Настройка элемента управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="1a3c1-110">To set up the BindingNavigator control</span></span>  
  
1.  <span data-ttu-id="1a3c1-111">Добавьте компонент <xref:System.Windows.Forms.BindingSource> с именем `bindingSource1` и два элемента управления <xref:System.Windows.Forms.TextBox> с именами `textBox1` и `textBox2`.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-111">Add a <xref:System.Windows.Forms.BindingSource> component named `bindingSource1` and two <xref:System.Windows.Forms.TextBox> controls named `textBox1` and `textBox2`.</span></span>  
  
2.  <span data-ttu-id="1a3c1-112">Свяжите `bindingSource1` с данными, а элементы управления текстового поля — с `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-112">Bind `bindingSource1` to data, and the textbox controls to `bindingSource1`.</span></span> <span data-ttu-id="1a3c1-113">Для этого вставьте приведенный ниже код в форму и вызовите `LoadData` из конструктора формы или метода обработки событий <xref:System.Windows.Forms.Form.Load>.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-113">To do this, paste the following code into your form and call `LoadData` from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="1a3c1-114">Добавьте элемент управления <xref:System.Windows.Forms.BindingNavigator> с именем `bindingNavigator1` в форму.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-114">Add a <xref:System.Windows.Forms.BindingNavigator> control named `bindingNavigator1` to your form.</span></span>  
  
4.  <span data-ttu-id="1a3c1-115">Присвойте свойству <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> элемента `bindingNavigator1` значение `bindingSource1`.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-115">Set the <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property for `bindingNavigator1` to `bindingSource1`.</span></span> <span data-ttu-id="1a3c1-116">Это можно сделать с помощью конструктора или в коде.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-116">You can do this with the designer or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="1a3c1-117">Пример</span><span class="sxs-lookup"><span data-stu-id="1a3c1-117">Example</span></span>  
 <span data-ttu-id="1a3c1-118">В примере кода ниже полностью представлены предыдущие шаги.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-118">The following code example is the complete example for the steps listed previously.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingNavigatorNavigate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingNavigatorNavigate/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1a3c1-119">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="1a3c1-119">Compiling the Code</span></span>  
 <span data-ttu-id="1a3c1-120">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="1a3c1-120">This example requires:</span></span>  
  
-   <span data-ttu-id="1a3c1-121">ссылки на сборки System, System.Data, System.Drawing, System.Windows.Forms и System.Xml.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-121">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="1a3c1-122">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="1a3c1-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1a3c1-123">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="1a3c1-123">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="1a3c1-124">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="1a3c1-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a3c1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="1a3c1-125">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [<span data-ttu-id="1a3c1-126">Элемент управления BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="1a3c1-126">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="1a3c1-127">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1a3c1-127">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
