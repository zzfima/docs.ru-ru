---
title: Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: daddbee9aa5eff55bf12a5d8c53ad59001a0c308
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612454"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="61e2b-102">Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="61e2b-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="61e2b-103">При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту.</span><span class="sxs-lookup"><span data-stu-id="61e2b-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="61e2b-104">Обычно подобная ситуация возникает на этапе разработки, когда данные недоступны, однако нужно, чтобы элементы управления с привязкой к данным отображали данные из открытого интерфейса типа.</span><span class="sxs-lookup"><span data-stu-id="61e2b-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="61e2b-105">Ниже описано, как создать новый <xref:System.Windows.Forms.BindingSource> то есть связанного с типом, а затем привязать одно из свойств типа к <xref:System.Windows.Forms.TextBox.Text%2A> свойство <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61e2b-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="61e2b-106">Привязка BindingSource к типу</span><span class="sxs-lookup"><span data-stu-id="61e2b-106">To bind the BindingSource to a type</span></span>  
  
1. <span data-ttu-id="61e2b-107">Создайте проект Windows Forms (**файл** > **New** > **проекта** > **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="61e2b-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="61e2b-108">В **разработки** Просмотр, перетащите <xref:System.Windows.Forms.BindingSource> компонента в форму.</span><span class="sxs-lookup"><span data-stu-id="61e2b-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3. <span data-ttu-id="61e2b-109">В **свойства** окно, нажмите кнопку со стрелкой <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="61e2b-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4. <span data-ttu-id="61e2b-110">В **редакторе типов пользовательского интерфейса DataSource** нажмите кнопку **Добавить источник данных проекта**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5. <span data-ttu-id="61e2b-111">На странице **Выбор типа источника данных** выберите тип **Объект** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6. <span data-ttu-id="61e2b-112">Выберите тип для привязки.</span><span class="sxs-lookup"><span data-stu-id="61e2b-112">Select the type to bind to:</span></span>  
  
    - <span data-ttu-id="61e2b-113">Если тип для привязки находится в текущем проекте либо сборка, содержащая этот тип, уже добавлена как ссылка, разверните узлы, а затем найдите и выберите желаемый тип.</span><span class="sxs-lookup"><span data-stu-id="61e2b-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="61e2b-114">-или-</span><span class="sxs-lookup"><span data-stu-id="61e2b-114">-or-</span></span>  
  
    - <span data-ttu-id="61e2b-115">Если тип для привязки находится в другой сборке, которой еще нет в списке ссылок, нажмите **Добавить ссылку** и выберите вкладку **Проекты**. Выберите проект, содержащий нужный вам бизнес-объект, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="61e2b-116">Этот проект будет отображаться в списке сборок, так что вы сможете развернуть узлы, а затем найти и выбрать желаемый тип.</span><span class="sxs-lookup"><span data-stu-id="61e2b-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="61e2b-117">Если тип, который нужно привязать, находится в инфраструктуре или сборке Майкрософт, снимите флажок **Скрыть сборки, начинающиеся с Microsoft или System**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7. <span data-ttu-id="61e2b-118">Щелкните **Далее**и затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-118">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="61e2b-119">Привязка элемента управления к BindingSource</span><span class="sxs-lookup"><span data-stu-id="61e2b-119">To bind the control to the BindingSource</span></span>  
  
1. <span data-ttu-id="61e2b-120">Добавьте на форму элемент <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61e2b-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2. <span data-ttu-id="61e2b-121">В окне **Свойства** разверните узел **(DataBindings)**.</span><span class="sxs-lookup"><span data-stu-id="61e2b-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3. <span data-ttu-id="61e2b-122">Щелкните стрелку рядом с полем <xref:System.Windows.Forms.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="61e2b-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4. <span data-ttu-id="61e2b-123">В **редактора типов пользовательского интерфейса DataSource**, разверните узел для <xref:System.Windows.Forms.BindingSource> добавленной ранее и выберите свойство типа, необходимо выполнить привязку к <xref:System.Windows.Forms.TextBox.Text%2A> свойство <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="61e2b-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e2b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="61e2b-124">See also</span></span>

- [<span data-ttu-id="61e2b-125">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="61e2b-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="61e2b-126">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="61e2b-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="61e2b-127">Привязка элементов управления к данным в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="61e2b-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
