---
title: Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 5069d7d3b5ef4c5b05159dac521d32f5be8abdd1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046045"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="91ce8-102">Практическое руководство. Привязка элемента управления Windows Forms к типу с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="91ce8-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>

<span data-ttu-id="91ce8-103">При создании элементов управления, взаимодействующих с данными, иногда бывает нужно привязать элемент управления к типу, а не к объекту.</span><span class="sxs-lookup"><span data-stu-id="91ce8-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="91ce8-104">Обычно подобная ситуация возникает на этапе разработки, когда данные недоступны, однако нужно, чтобы элементы управления с привязкой к данным отображали данные из открытого интерфейса типа.</span><span class="sxs-lookup"><span data-stu-id="91ce8-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="91ce8-105">В следующих процедурах показано, как создать новый <xref:System.Windows.Forms.BindingSource> объект, привязанный к типу, а затем как привязать одно из свойств типа <xref:System.Windows.Forms.TextBox.Text%2A> к свойству объекта <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="91ce8-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>

### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="91ce8-106">Привязка BindingSource к типу</span><span class="sxs-lookup"><span data-stu-id="91ce8-106">To bind the BindingSource to a type</span></span>

1. <span data-ttu-id="91ce8-107">Создание проекта Windows Forms (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic** > **классический рабочий** стол >   **Windows Forms приложение**).</span><span class="sxs-lookup"><span data-stu-id="91ce8-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="91ce8-108">В режиме **конструктора** перетащите <xref:System.Windows.Forms.BindingSource> компонент на форму.</span><span class="sxs-lookup"><span data-stu-id="91ce8-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>

3. <span data-ttu-id="91ce8-109">В окне **Свойства** щелкните стрелку <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="91ce8-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>

4. <span data-ttu-id="91ce8-110">В **редакторе типов пользовательского интерфейса DataSource** нажмите кнопку **Добавить источник данных проекта**.</span><span class="sxs-lookup"><span data-stu-id="91ce8-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>

5. <span data-ttu-id="91ce8-111">На странице **Выбор типа источника данных** выберите тип **Объект** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="91ce8-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>

6. <span data-ttu-id="91ce8-112">Выберите тип для привязки.</span><span class="sxs-lookup"><span data-stu-id="91ce8-112">Select the type to bind to:</span></span>

    - <span data-ttu-id="91ce8-113">Если тип для привязки находится в текущем проекте либо сборка, содержащая этот тип, уже добавлена как ссылка, разверните узлы, а затем найдите и выберите желаемый тип.</span><span class="sxs-lookup"><span data-stu-id="91ce8-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>

      <span data-ttu-id="91ce8-114">\-или-</span><span class="sxs-lookup"><span data-stu-id="91ce8-114">\-or-</span></span>

    - <span data-ttu-id="91ce8-115">Если тип для привязки находится в другой сборке, которой еще нет в списке ссылок, нажмите **Добавить ссылку** и выберите вкладку **Проекты**. Выберите проект, содержащий нужный вам бизнес-объект, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="91ce8-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="91ce8-116">Этот проект будет отображаться в списке сборок, так что вы сможете развернуть узлы, а затем найти и выбрать желаемый тип.</span><span class="sxs-lookup"><span data-stu-id="91ce8-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>

      > [!NOTE]
      > <span data-ttu-id="91ce8-117">Если тип, который нужно привязать, находится в инфраструктуре или сборке Майкрософт, снимите флажок **Скрыть сборки, начинающиеся с Microsoft или System**.</span><span class="sxs-lookup"><span data-stu-id="91ce8-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>

7. <span data-ttu-id="91ce8-118">Щелкните **Далее**и затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="91ce8-118">Click **Next**, and then click **Finish**.</span></span>

### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="91ce8-119">Привязка элемента управления к BindingSource</span><span class="sxs-lookup"><span data-stu-id="91ce8-119">To bind the control to the BindingSource</span></span>

1. <span data-ttu-id="91ce8-120">Добавьте на форму элемент <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="91ce8-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>

2. <span data-ttu-id="91ce8-121">В окне **Свойства** разверните узел **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="91ce8-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>

3. <span data-ttu-id="91ce8-122">Щелкните стрелку рядом <xref:System.Windows.Forms.TextBox.Text%2A> со свойством.</span><span class="sxs-lookup"><span data-stu-id="91ce8-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

4. <span data-ttu-id="91ce8-123">В окне **Редактор типов пользовательского интерфейса источника данных**разверните узел <xref:System.Windows.Forms.BindingSource> добавленного ранее и выберите свойство связанного типа, которое необходимо привязать к <xref:System.Windows.Forms.TextBox.Text%2A> свойству <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="91ce8-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>

## <a name="see-also"></a><span data-ttu-id="91ce8-124">См. также</span><span class="sxs-lookup"><span data-stu-id="91ce8-124">See also</span></span>

- [<span data-ttu-id="91ce8-125">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="91ce8-125">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="91ce8-126">Практическое руководство. Привязка элемента управления Windows Forms к типу</span><span class="sxs-lookup"><span data-stu-id="91ce8-126">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
- [<span data-ttu-id="91ce8-127">Привязка элементов управления к данным в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="91ce8-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
